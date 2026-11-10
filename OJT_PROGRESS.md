# FOSSology OJT Progress Record

## Student and project

- Student: Pinank Shah
- Project: FOSSology
- Repository: `pinankshah8-Aa/fossology`
- OJT branch: `ojt-setup`
- Review date: 10 November 2026

## Work completed

### 1. Git and GitHub workflow

- Forked the official `fossology/fossology` repository.
- Cloned the fork to the local machine.
- Created the separate `ojt-setup` branch.
- Added `OJT_SETUP.md` as the initial OJT record.
- Committed and pushed the branch to GitHub.
- Verified that the branch is one commit ahead of the fork's `master` branch before this progress update.

Commands used:

```bash
git clone https://github.com/pinankshah8-Aa/fossology.git
cd fossology
git switch -c ojt-setup
git add OJT_SETUP.md
git commit -m "docs: add initial OJT learning notes"
git push -u origin ojt-setup
```

### 2. Local FOSSology execution

The FOSSology Docker image did not provide a native Apple Silicon manifest. The container was therefore started with AMD64 emulation:

```bash
docker run --platform linux/amd64 -d \
  --name fossology-ojt \
  -p 127.0.0.1:8081:80 \
  fossology/fossology:latest
```

Before running the command, Docker Desktop must be open and the Docker daemon must be running. The earlier `docker.sock` connection error was caused by the daemon not being available.

The web interface was verified at:

```text
http://localhost:8081/repo/
```

The FOSSology Browse page loaded successfully and the local user was logged in as `fossy`.

### 3. What I learned

- A fork is my GitHub copy of the upstream project.
- A clone is the working copy on my computer.
- A branch keeps OJT changes separate from `master`.
- A commit records a focused change and its purpose.
- A push publishes local commits to the fork.
- Open-source work requires reading contribution rules, checking for existing work, making focused changes, testing them, and responding to review feedback.
- Issue selection also requires a collision check. I should not start an issue that is assigned, already has a pull request, or has another contributor actively preparing a fix.

## Current verification status

- [x] Official repository forked
- [x] Fork cloned locally
- [x] OJT branch created
- [x] Initial commit created and pushed
- [x] Docker Desktop and container execution verified
- [x] FOSSology web interface opened at localhost
- [ ] Upload a small sample archive
- [ ] Schedule a basic license scan
- [ ] Review the generated job and license results
- [ ] Record screenshots for the OJT video
- [ ] Select an unassigned, collision-free upstream issue

## Next practical exercise

1. Open `http://localhost:8081/repo/`.
2. Select **Upload** and upload a small open-source archive.
3. Schedule the **Nomos** and **Ojo** agents.
4. Open **Jobs** and wait for the scan to complete.
5. Review the detected licenses in **Browse**.
6. Capture only the four screens needed for the OJT video: terminal clone/branch, GitHub commit, running FOSSology page, and completed scan result.

## Upstream contribution rule

The current public issue list was reviewed before choosing implementation work. The recent small issues already have an assignee, an active contributor, a candidate fix, or an open pull request. No upstream implementation should be started until one bounded issue passes the ownership and collision checks.
