# osint_investigator_ctf_challenges

CTF challenges for [ctfcli](https://github.com/CTFd/ctfcli) / [multi-ctfd-deploy](https://github.com/Manta-Epitech-Academy/multi-ctfd-deploy).

**Repository:** https://github.com/Manta-Epitech-Academy/osint_investigator_ctf_challenges

## Contents

- **31 challenges** under `challenges/`
- **`index.html`** — optional CTFd home page fragment (French onboarding for players); deployed with [deploy_challenges](https://github.com/kevin-cazal/deploy_challenges) when present at repo root ([format](https://github.com/kevin-cazal/deploy_challenges/blob/main/CHALLENGE_REPOSITORY.md))

## Missing assets

Challenges whose `files:` list references a file that is not yet in the repo (or is empty):

| Challenge | Folder | Status |
|-----------|--------|--------|
| QRCode inversé | `challenges/steganography/qrcode_inverse/` | **Missing asset** — no QR image in the Notion export; add image and update `challenge.yml` `files:` before deploy |

All other challenges with a `files:` section have their assets present locally.

## Placeholder flags

Three CTFD.md draft challenges still use placeholder flags in `private/*.gpg` until validated:

| Challenge | Placeholder |
|-----------|-------------|
| Marque du collier | `ctf{TODO_KONG}` |
| Message dans le nonogramme | `ctf{TODO_NONOGRAMME}` |
| QRCode inversé | `ctf{TODO_QR_INVERSE}` |

Run `./decrypt.sh`, edit `private/flag.txt`, then `./encrypt.sh` before deploy. These challenges use `state: hidden` in `challenge.yml` until assets and flags are ready.

## Secrets

Flags and writeups are GPG-encrypted in `private/*.gpg` only (never commit `private/flag.txt`, `private/writeup.md`, or `.gpg-passphrase`).

The **Tutoriel** challenge intentionally includes its flag in the public `description` (same as on the live platform).

```bash
export GPG_PASSPHRASE="$(cat .gpg-passphrase)"
./decrypt.sh    # before editing flags/writeups
./encrypt.sh    # before git commit
```

## Deploy

```bash
export GPG_PASSPHRASE="$(cat .gpg-passphrase)"
./decrypt.sh
cd ../multi-ctfd-deploy
python3 deploy_challenges.py https://github.com/Manta-Epitech-Academy/osint_investigator_ctf_challenges.git --subdir challenges --instance <name>
```

Or from a local clone:

```bash
python3 deploy_challenges.py ../epitech_2025_ctf_challenges --no-clone --subdir challenges --instance <name>
```

Configure category unlock chains and other CTFd relationships in the admin UI if needed. Every challenge except **Tutoriel** declares `requirements: ["Tutoriel"]` in its `challenge.yml` (ctfcli format).
