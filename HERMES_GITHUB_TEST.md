# Hermes GitHub Connection Test

## Status: ✅ Connected and Operational

### Authorized Account
- Login: `stroim20202-gif`
- Verified via: `node ~/.hermes/tools/gh-api.mjs GET /user`

### Available Permissions
- ✅ Contents read/write
- ✅ Issues read/write
- ✅ Pull requests read/create
- ✅ Repository metadata read
- ⚠️ Repository creation via API tested separately
- ⚠️ Workflow triggers - not tested

### Git Operations Verified
- ✅ `git clone` via HTTPS with credential store
- ✅ `git switch -c <branch>` 
- ✅ `git add -A` + `git commit -m "..."`
- ✅ `git push -u origin <branch>` (via credential store, no interactive auth)

### API Access Routes
- Repo: `GET /repos/stroim20202-gif/hello-github`
- Branches: `GET /repos/stroim20202-gif/hello-github/branches`
- Issues: `GET /repos/stroim20202-gif/hello-github/issues`
- PRs: `GET /repos/stroim20202-gif/hello-github/pulls`
- Commit status: `GET /repos/stroim20202-gif/hello-github/commits/<sha>/status`

### Notes
- Token stored in `~/.git-credentials` via `credential.helper=store`
- Proxy (SOCKS5 127.0.0.1:10815) may block direct `git clone` - use credential helper or adjust network
- `gh` CLI not available in sandbox; all operations via `node ~/.hermes/tools/gh-api.mjs`
- Fine-grained PAT scope: Contents/Issues/Pull requests: write (90-day validity)

### Test Checklist (completed 2026-11-09)
1. ✅ Node.js and git available
2. ✅ GitHub API authorization confirmed (stroim20202-gif)
3. ✅ Repository hello-github accessible
4. ✅ Clone operation successful
5. ✅ Branch creation and file modifications tested
6. ⏳ Push + PR workflow pending user confirmation
