# openGym fork — b1

**Upstream:** https://github.com/DuarteSantos8/openGym.git
**Fork (origin):** https://github.com/lainaireau/open-gym.git

## Pin

The `b1` branch starts at upstream commit `e4a68a9` (openGym 1.4.5).
b1droid records this commit as the submodule pin; whatever b1droid records
is what the TS140 builds.

## Branch discipline

- `main` is a clean copy of upstream. **Never commit to `main`.**
- All b1 changes are ordinary commits on `b1`.
- Git always knows what we changed and an upstream update is a merge.

## Upstream merge checklist

1. `git fetch upstream`
2. Fast-forward `main`: `git checkout main && git merge upstream/main`
3. Merge an upstream tag into `b1`: `git checkout b1 && git merge <tag>`
4. Take upstream's lock files **as they are** (don't edit them).
5. Refresh the base-image digests (ticket 73).
6. Run the tests (ticket 71), the route check (ticket 74) and the
   supply-chain check (ticket 75), and record the fixtures again (ticket 81).
7. Move b1droid's submodule pin to the new `b1` commit and commit it with
   the new upstream version in the message.
