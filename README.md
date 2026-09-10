# Personal Loon Rules

This repository contains routing rules only. It contains no nodes, subscription URLs, accounts, passwords, or certificates.

`loon-routing.conf` uses blackmatrix7/ios_rule_script Loon-native remote rules. The upstream rules update in Loon; this repository is only for maintaining your selected services, rule order, and policy-group name. Its remote-rule lines use Loon's official minimal syntax: `URL,policy=...,enabled=true`.

Use `loon-routing.conf` in Loon's configuration import/subscription flow. Do not add the `.conf` URL from the rule-subscription screen: that screen expects actual lines such as `DOMAIN-SUFFIX,example.com`, so a configuration file produces "no usable rules". The `.conf` itself contains the remote rule definitions and should be loaded as a configuration.

Before importing, replace `PROXY` with the policy group name that exists in your Loon profile.

The Microsoft rule defaults to `PROXY` for Copilot and international Microsoft services.

After pushing this repository to the private GitHub repository `xxbcisco/loon-config`, its Raw URL will be:

```text
https://raw.githubusercontent.com/xxbcisco/loon-config/main/loon-routing.conf
```

GitHub private-repository Raw URLs require GitHub authentication. Loon cannot authenticate to GitHub when fetching a remote configuration, so this URL will not work as a Loon remote URL while the repository remains private. Use a public rules-only repository for direct Loon URL imports. This configuration does not contain nodes, subscription URLs, or account data.

Importing a configuration can replace the current profile in some Loon flows. Keep your existing node subscription and local settings. When Loon shows a replacement warning, merge the `[Remote Rule]` entries into the current configuration instead of replacing it.
