# Bolt Performance Journal

## 2026-03-22 - Fix socket network calls in unit tests
**Learning:** In worker unit tests (`test_copy_svg_langs_worker.py`), missing service fixtures allowed `FilesService.download_and_save` to make real network requests to Wikimedia Commons, causing 10s socket timeout delays per test.
**Action:** Set `autouse=True` on worker service mock fixtures to guarantee that all test methods consistently mock file downloads and network interactions.
