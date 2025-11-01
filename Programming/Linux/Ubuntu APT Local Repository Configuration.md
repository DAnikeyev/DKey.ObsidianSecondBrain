---
date_added: 2025-11-01
tags: [linux, ubuntu, apt, package-management, local-repository]
---
Up: [[Main]]
___

# Ubuntu APT Local Repository Configuration

## Overview
This note documents how to configure Ubuntu's APT package manager to use a local repository instead of the default Ubuntu archive repositories.

## Problem Context
When running Ubuntu in a container or offline environment (e.g., at `/app` in a Docker container), you may need to configure APT to use a local repository located on the filesystem instead of accessing remote Ubuntu repositories.

## Prerequisites
- Local repository must be properly structured with:
  - Package files (`.deb`)
  - Package index files (`Packages.gz`, `Release`, etc.)
  - Proper directory structure

## Solution: Configuring Local Repository

### Current Ubuntu Sources File Location
- Modern Ubuntu (22.04+): `/etc/apt/sources.list.d/ubuntu.sources`
- Uses DEB822 format

### Steps to Replace with Local Repository

#### 1. Backup Original Sources
```bash
sudo cp /etc/apt/sources.list.d/ubuntu.sources /etc/apt/sources.list.d/ubuntu.sources.backup
```

#### 2. Create New Sources Configuration

Replace the contents of `/etc/apt/sources.list.d/ubuntu.sources` with:

```
Types: deb
URIs: file:///app/local-repo
Suites: ./
Components:
Trusted: yes
```

**Important Configuration Notes:**
- `URIs: file:///app/local-repo` - Points to your local repository path (the URI format is `file://` followed by the absolute path `/app/local-repo`)
- `Suites: ./` - The dot-slash indicates a flat repository structure
- `Components:` - Left empty for flat repositories
- `Trusted: yes` - Required for local repositories without GPG signatures

#### 3. Alternative: Traditional sources.list Format

If you prefer the traditional format, you can use `/etc/apt/sources.list` instead:

```
deb [trusted=yes] file:///app/local-repo ./
```

#### 4. Update Package Cache
```bash
sudo apt update
```

### Verifying the Configuration

Check that APT recognizes your local repository:
```bash
apt-cache policy
apt list --all-versions
```

### Local Repository Structure

Your local repository at `/app/local-repo` should contain:
```
/app/local-repo/
├── Packages (or Packages.gz)
├── Release
└── *.deb files
```

### Creating a Local Repository

If you need to create a local repository from scratch:

```bash
# Navigate to your repository directory
cd /app/local-repo

# Generate Packages index
# Note: /dev/null as second parameter means no override files are used
dpkg-scanpackages . /dev/null | gzip -9c > Packages.gz

# Create uncompressed version (optional but recommended)
dpkg-scanpackages . /dev/null > Packages

# Create Release file (optional)
cat > Release << EOF
Archive: local
Component: main
Origin: Local Repository
Label: Local Repository
Architecture: amd64
EOF
```

## Troubleshooting

### Issue: "Release file not found"
- Ensure the repository path is correct
- Verify `Packages.gz` or `Packages` file exists
- Check file permissions

### Issue: "GPG signature verification failed"
- Add `Trusted: yes` to the DEB822 format
- Or use `[trusted=yes]` in traditional format

### Issue: Packages not installing
- Verify package architecture matches your system
- Check package dependencies are available in local repo
- Run `apt-cache policy <package-name>` to see available versions

## References
- [Debian Repository Format](https://wiki.debian.org/DebianRepository/Format)
- [APT Sources List DEB822 Format](https://repolib.readthedocs.io/en/latest/deb822-format.html)
- [Creating Local APT Repository](https://help.ubuntu.com/community/Repositories/Personal)

## Related Notes
- [[Package Management]]
- [[Docker Container Configuration]]
- [[Ubuntu System Administration]]
