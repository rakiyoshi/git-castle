# git-castle

## How to integrate GPG with 1Password
Ref: https://bmaingret.github.io/blog/2022-02-15-1Password-gpg-git-seamless-commits-signing

```fish:.fish_config.local
function gpg_cache
    gpg-connect-agent /bye &> /dev/null
    eval $(op signin)
    op get item ${ITEM ID} --fields password | /usr/lib/gnupg2/gpg-preset-passphrase --preset ${Key grip}
end
gpg_cache
```
