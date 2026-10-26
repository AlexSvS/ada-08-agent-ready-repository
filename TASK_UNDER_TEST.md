# Task Under Test

Change ID: CR-001

## Goal
Fix customer JSON validation so that records with a Boolean value (`true` or `false`) in the `id` field are rejected as invalid customer records.

In Python, Boolean values are a subclass of integers, so the current `isinstance(record["id"], int)` check incorrectly accepts JSON Boolean IDs. Update the validation logic in `src/customer_search/storage.py` to reject Boolean IDs while continuing to accept valid integer IDs.

Add automated tests in `tests/test_storage.py` to verify that Boolean IDs raise `StorageError` and that valid integer IDs continue to be accepted.

## Requirements Covered
- FR-06
- AC-08
- VR-03
- EH-02

## Verification
- Add a storage unit test using a JSON record whose `id` is `true` and verify that `CustomerStorage.read_all()` raises `StorageError`.
- Add a corresponding test for `id: false` or parameterize the test to cover both Boolean values.
- Verify that a valid integer ID, such as `1`, remains accepted.
- Run `python -m pytest tests/test_storage.py` and confirm the relevant tests pass.
- Run the full test suite with `python -m pytest` to check for regressions.
- Verify through the CLI that a JSON file containing a Boolean ID produces a storage error and a non-zero exit code.

## Constraints
- Use `REQUIREMENTS.md` and `SPEC.md` as the source of truth.
- Keep changes scoped to this task.
- Do not redefine requirements in this file.
- Do not modify `REQUIREMENTS.md` or `SPEC.md`.
- Preserve the existing layered architecture and error-handling behavior.
- Do not add external dependencies or weaken existing tests.