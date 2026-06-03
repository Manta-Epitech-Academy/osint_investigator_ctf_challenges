# osint_investigator_ctf_challenges

CTF challenges for [ctfcli](https://github.com/CTFd/ctfcli) / [multi-ctfd-deploy](https://github.com/Manta-Epitech-Academy/multi-ctfd-deploy).

**Repository:** https://github.com/Manta-Epitech-Academy/osint_investigator_ctf_challenges

## Contents

- **27 challenges** under `challenges/`

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

Configure challenge prerequisites and next-challenge unlocks in the CTFd admin UI.
