# Shared JDT LS UI evidence

Synthetic OpenIDEA browser fixture, no company projects or settings.

- Before: upstream/main d17f6755, Java settings.
- After: opt-in Share JDT LS across builds, applied.
- Recording: enable and Apply; uncheck and Cancel; reopen to verify the applied setting; native Workspace project scope is disabled, while global preferences remain editable.

These screenshots and recording verify the settings UI only. Real JDT LS / Gradle integration is verified by the integration test described in the pull request.
