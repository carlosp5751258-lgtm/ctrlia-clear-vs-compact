# /clear, /compact and friends: cheat sheet

```text
/context                         # how much have I used and what weighs most?
/clear task-name                 # new unrelated task (free; /resume brings it back)
/compact keep X, Y and Z         # same task, less context
/rewind  (or Esc Esc)            # Summarize from here / up to here
/autocompact 500k                # compact earlier (auto = model default)
/branch try-another-idea         # fork the conversation
/config                          # Idle compaction row
```

- Task unrelated to what came before? `/clear`. Same task and the context is heavy? `/compact` with instructions.
- Want to throw away a wrong path? `/rewind` to an earlier turn, better than compacting.
- Compact at a natural break, not on a huge, cold session.
- Before a big compaction or stepping away, save the state to `NOTES.md` (`prompt-notes.en.txt`).
