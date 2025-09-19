# bash-scripts
Basic bash scripts for the day to day

The lost art of the shell pros and cons of different shells and why I'm focused on bash
| Shell                      | Style/Focus                        |                POSIX for scripts? | Interactive strengths                                          | Scripting strengths                                     | Cons / Gotchas                                                                        | Best for                                     |
| -------------------------- | ---------------------------------- | --------------------------------: | -------------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------------------------------------- | -------------------------------------------- |
| **bash**                   | General-purpose, **de-facto standard** | **Mostly** (with many extensions) | ✅ Widely known; good readline/vi-mode; programmable completion | ✅ Mature features, arrays, brace expansion, coprocesses | ⚠️ Some features non-portable; slower than dash for tiny scripts                      | Everyday interactive + general scripting     |
| **zsh**                    | Power user, highly customizable    |          **Largely**, with quirks | ✅ Best-in-class completion; globbing; prompts; plugins         | ✅ Rich features (assoc arrays, options)                 | ⚠️ Slight POSIX differences; heavy with plugins                                       | Interactive power users                      |
| **fish**                   | User-friendly, modern              |                            **No** | ✅ Great autosuggestions; minimal config                        | ➖ Clean but fish-only language                          | ⚠️ Not POSIX-compatible                                                               | New users, ergonomic interactive work        |
| **ksh93**                  | Classic Korn shell (newer AT\&T)   |                           **Yes** | ✅ Solid job control; vi-mode                                   | ✅ Strong arithmetic, discipline functions               | ⚠️ Fewer modern niceties vs zsh; variant differences                                  | Robust, portable scripting                   |
| **ksh88 (original ksh)**   | Original KornShell (1988)          |                           **Yes** | ➕ Lean, predictable; vi-mode                                   | ✅ Good POSIX scripting baseline                         | ⚠️ Older; missing ksh93 features (assoc arrays, more arithmetic); availability varies | Legacy systems, strict POSIX-era portability |
| **mksh**                   | Modernized ksh (lightweight)       |                           **Yes** | ➕ Fast startup                                                 | ✅ Good POSIX/ksh scripting                              | ⚠️ Fewer interactive bells/whistles                                                   | Lightweight systems, init scripts            |
| **dash**                   | Minimal POSIX `/bin/sh`            |                           **Yes** | ➖ Spartan                                                      | ✅ Extremely fast for POSIX scripts                      | ⚠️ Meant for scripts; limited interactive features                                    | System scripts, speed, portability           |
| **BusyBox ash**            | BusyBox’s small sh                 |                    **Yes** (most) | ➕ Tiny footprint                                               | ✅ Good for boot scripts                                 | ⚠️ Missing conveniences; BusyBox quirks                                               | Embedded/rescue environments                 |
| **tcsh** (C shell variant) | C-like syntax                      |                            **No** | ➕ Completion/history features                                  | ➖ Legacy scripting                                      | ⚠️ Error-prone scripting semantics                                                    | Legacy users/environments                    |
| **csh** (BSD C shell)      | C-like syntax, older than tcsh     |                            **No** | ➕ Familiar to old-school users                                 | ➖ Limited, quirky scripting; poor error handling        | ⚠️ Not POSIX; many gotchas (flow control, quoting)                                    | Historical/legacy setups only                |
| **yash**                   | Strict POSIX sh with extras        |                           **Yes** | ➕ Consistent behavior                                          | ✅ Great for portable sh scripts                         | ⚠️ Less common; few interactive perks                                                 | Testing/authoring portable sh                |
| **nushell**                | Data/table-oriented pipelines      |                            **No** | ✅ Structured data model                                        | ➕ Modern scripting paradigm                             | ⚠️ Not a drop-in for POSIX; young ecosystem                                           | Data wrangling workflows                     |
| **xonsh**                  | Python-powered shell               |                            **No** | ✅ Mix Python + shell                                           | ➕ Use Python libs inline                                | ⚠️ Startup overhead; niche                                                            | Python-heavy interactive work                |
| **oil shell (osh)**        | Safer, modernized sh               |                 **Aims at POSIX** | ➕ Better errors; evolving                                      | ➕ Migration path from sh                                | ⚠️ Not widely installed yet                                                           | Safer sh experiments                         |


Scripts:

sd - formatted side by side diff
<pre>
  >sd file1.py file2.py
  OUTPUT:
  
------------------------------------------------------+------------------------------------------------------
        File file1.py                                 | File file2.py
------------------------------------------------------+------------------------------------------------------
    39	gain_r = 9.5                                  |	gain_r = 1.
    40	gain_d = 9.5                                  |	gain_d = 1.
    41	gain_c = 4.0                                  |	gain_c = 1.
------------------------------------------------------+-----------------------------------------------------
</pre>
