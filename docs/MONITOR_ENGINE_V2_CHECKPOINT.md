# Monitor engine v2 — isolated development checkpoint (2026-10-19)

**Owner:** ChatGPT engineering continuation, distinct from the currently running original Windows daily public-demo monitor.

**What is implemented:** Portable Python 3.11+ standard-library monitoring engine and tests. Source bundle: ChatGPT conversation artifact `openapi-monitor-service-v2-pilot.zip`. New code is NOT deployed or running on a scheduler. 13 synthetic unit tests pass in Python 3.13 including replays, repeated transitions, failures, and URL allowlist. It uses persistent SQLite with atomic baseline/event transactions and the official `oasdiff` command for changed content. The two configured URLs are oasdiff's public OpenAPI demo files, not customer endpoints.

**Current real product:** https://openapi-change-review-site.onrender.com/ — browser-only static limited JSON comparison plus email link for pilot interest. Customer alert delivery and full hosted monitoring are NOT available. No billing or pricing activation. Support/pilot Gmail automated workflow is already separate and should not be duplicated.

**External hard constraint:** Render Free web services spin down and lose local SQLite on restart; see https://render.com/docs/free. Do not deploy this database there or claim persistence. Preserve $0 incremental spending and no live charges.

**Existing Windows worker:** `C:\Users\bottl\Documents\Jake Operator\AutonomousRevenue\api-monitor\monitor.py` and Windows task `Jake Revenue API Monitor Pilot`, once daily 09:00 America/Denver. Existing task must not be replaced until new engine passes actual Windows `oasdiff` end-to-end acceptance.

**Next safe milestone:** Recover/source the packaged engine, run pinned real oasdiff engine on official fixtures and two public URLs in isolated state, verify first baseline, second unchanged check, simulated breaking change, and failure rollback. Do not retry an operation rejected by platform safety through a different executor. Once passed, stage one separately owned watch loop and improve opt-in onboarding/secure customer URL validation. Stripe product creation in sandbox was safety-blocked in an earlier turn; do not replay via scripts or alternate tools.

**Do not claim:** production running, customer service, Stripe checkout active, income, unlimited cloud persistence, autonomous progress based on heartbeat alone.

**Completion criterion:** actual opt-in customer source is monitored from baseline to a detected change and one verifiably delivered alert, with retry and cancellation, before paid launch.
