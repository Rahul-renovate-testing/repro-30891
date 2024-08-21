## Expected Behaviour

Label `xmldoc` should be added to the update PRs created by the bot which update `xmldoc` dependency.

## Current Behaviour

Getting a invalid configuration warning. 

## Cause

https://github.com/renovatebot/renovate/blob/d88debdcc0064c3893509ed36d6aaff45919bccc/lib/config/migrations/custom/package-rules-migration.ts#L70-L76

`matchPackagePrefixes` only gets migrated to `matchpackageNames` if its an array. But in out case its a string, in which it just gets deleted from the package rule.

## Possible Fix

Migrate strings too.
