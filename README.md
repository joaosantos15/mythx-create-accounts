# mythx-create-accounts

MythX script for batch creation of user accounts.

### Installation
1.  Install [NodeJS](https://nodejs.org/en/).
2.  Install script dependencies executing in its root folder:
    ```bash
    $ npm install
    ```
3.  Optionally, link the script as a global command, executing in its root:
    ```bash
    $ npm link
    ```
    after that you can call the script as `$ mythx-create-accounts` from any
    path on your machine. Otherwise you should call with the full path, e.g.
    from the root folder of the script repo: `$ ./bin/mythx-create-accounts`.

### Usage
Minimalistic example: create 10 users with `Professional` role in
production MythX API:
```bash
$ mythx-create-accounts -u <YOUR_MYTHX_USER_ID> -p <YOUR_MYTHX_PASSWORD> -r Professional -n 10
```
Credentials for created accounts will be stored into `accounts.txt` file
in the current working directory.

You can authenticate with Ethereum address and password, like so:
```bash
$ mythx-create-accounts -e <YOUR_ETH_ADDRESS> -p <YOUR_MYTHX_PASSWORD> -r Professional --owner-partner-id <PARNTER_USER_ID> -n 10
```

Here is the full list of supported options:

| Option               | Alias | Argument                                      |
| -------------------- | ----- | --------------------------------------------- |
| `--user-id`          | `-u`  | MythX user ID to authorize the operation. Either this, or `-e` option must be provided. |
| `--user-eth-address` | `-e`  | Ethereum address to authorize the operation. Either this, or `-u` option must be provided. |
| `--password`         | `-p`  | MythX password of the user specified by `-e` or `-u` option. |
| `--roles`            | `-r`  | Optional. Whitespace separated array of roles to assign to created users; e.g. `-r Professional`, or `-r Free trusted_user`. Defaults to no roles. |
| `--owner-partner-id` |       | Optional. User ID of the partner responsible for the newly created accounts for billing purposes.
| `--number`           | `-n`  | Optional. The number of accounts to create. Defaults to `1`. |
| `--output`           | `-o`  | Optional. Name of the file to write credentials for created accounts. Defaults to `accounts.txt`. |
| `--api`              | `-a`  | Optional. Base API URL. Defaults to `https://api.mythx.io/v1` (production API). |
| `--label`            |       | Optional. `label` to assign to created accounts. |
| `--privateLabel`     |       | Optional. `privateLabel` to assign to created accounts. |
| `--help`             | `-h`  | Print usage information and exit. |     
