# The Dark Side of Open Source

## Solar Winds Supply Chain Attack
1. Attacker breached Solar Winds network
2. Injected malicious code into the dependency chain
3. Compromised many downstream consumers

Developers **can't** read all lines of code they depend on.

Average days until malicious packages are discovered by the community: `209`

## The Ledger Supply Chain Attack - December 2023

Former employees NPM account still had access to Ledger. Hackers used the former employees npm credentials on their compromised laptop to publish malicious code to Ledger's NPM package and steal user's crypto currency.

```js
import { loadConnectKit } from '@ledgerhq/connect-kit-loader'
const connectKit = await loadConnectKit()
```

This code depends on a CDN so that Ledger could release code immediately without requiring users to update.

### Lessons Learned
1. Don't hotlink to JS CDNs from within npm packages, bypassing lockfiles. **Related**: Do not use http, git, or GitHub dependencies within package.json.
2. Minimize npm publish access
  - Audit NPM access regularly
  - Rigorous checklist-based process for offboarding.
  - Use GitHub Actions publish workflow so no individual developer needs publish access.
3. Do not use packages that remotely load code and bypass lockfiles.
4. Vet dependencies.
5. Use fewer dependencies.

Snyk Advisor did not know about the attack for more than 12 hours after.

Developers & security teams are drowning in a flood of meaningless alerts
- `npm audit`

## npm audit: broken by design
Both sends too many and not enough alerts

Socket AI - an LLM to detect security problems within dependencies, even obfuscated code.
