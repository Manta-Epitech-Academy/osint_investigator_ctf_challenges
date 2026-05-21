# epitech_2025_ctf_challenges

CTF challenges for [ctfcli](https://github.com/CTFd/ctfcli) / [multi-ctfd-deploy](../multi-ctfd-deploy), generated from the Epitech Academy CTFd backup and Notion instructor solutions.

## Contents

- **29 challenges** under `challenges/` (23 from `backup/`, 6 scaffolded from Notion only)
- Prerequisites: `tools/requirements.json`
- Next-unlock chain: `tools/next_unlock.json`
- Missing player files: `tools/missing_assets.json`

## Secrets

Flags and writeups are GPG-encrypted in `private/*.gpg`. Passphrase in `.gpg-passphrase` (gitignored).

```bash
export GPG_PASSPHRASE="$(cat .gpg-passphrase)"
./decrypt.sh    # before editing flags/writeups
./encrypt.sh    # before git commit
```

## Regenerate

```bash
python3 tools/convert_notion_backup_to_ctfd.py
export GPG_PASSPHRASE="$(cat .gpg-passphrase)"
./encrypt.sh
```

Sources: `../ExportBlock-c2cfd994-9870-45bc-a09a-5463b7a5c08c-Part-1.zip`, `../backup/`.

## Deploy

```bash
export GPG_PASSPHRASE="$(cat .gpg-passphrase)"
./decrypt.sh
cd ../multi-ctfd-deploy
python3 deploy_challenges.py ../epitech_2025_ctf_challenges --subdir challenges --instance <name>
```

Configure challenge prerequisites and `next_id` unlocks in CTFd admin using the JSON files in `tools/`.

## Description-only challenges (awaiting assets)

See `tools/missing_assets.json`: Fichiers fantômes, Enquête moléculaire, Sonagram, Encre sympathique, Retour dans le passé, Un simple pont.

Drop files into the challenge folder, add them under `files:` in `challenge.yml`, then re-encrypt and redeploy.
