# PR #1413: independent Gradle builds

Public synthetic demo for [l0ng-ai/openidea#1413](https://github.com/l0ng-ai/openidea/pull/1413), tested with commit `0b71f96` on macOS 15.2 / Apple Silicon and Gradle 8.10.1.

[Download the portable demo](independent-gradle-demo.zip) or [browse its source](demo-source/independent-gradle-demo). The parent folder has no Gradle build; alpha and beta are separate builds, each with the same `:app:identify` task path. The task only prints its owning build and project. No company code, databases, credentials or application services are used.

## Native verification

These are unmodified screenshots from the native application, showing states during one operation sequence. They are not mockups, an upstream-versus-feature comparison, or a continuous video.

| Step | Observed result | Evidence |
|---|---|---|
| Initial open | Automatic discovery shows alpha | [01](01-initial.png) |
| Link beta | Two independent roots, each with an app project | [02](02-linked.png) |
| Run alpha/app identify | BUILD=alpha;PROJECT=:app, exit 0 | [03](03-alpha-run.png) |
| Run beta/app identify | BUILD=beta;PROJECT=:app, exit 0 | [04](04-beta-run.png) |
| Unlink both | No Gradle projects; Link remains available; files retained | [05](05-unlinked.png) |
| Relink and reopen | Both roots and app projects restored | [06](06-reopened.png) |

Java launcher warnings are visible in the run captures; both tasks completed successfully. Screenshots were reviewed to exclude company content, credentials and user home paths. The ZIP excludes IDE state and build caches. The Gradle wrapper may download its public distribution on first use.

## Native video

https://github.com/user-attachments/assets/6845cd37-73d3-44ab-be7b-abec83f31ad2

[Download MP4](gradle-linkage-demo.mp4). This 60-second recording shows real native UI actions at original speed. Only the idle tail is trimmed; two local home-path snippets in launcher warnings are visibly masked. Task actions and results are unchanged. No audio is included.
