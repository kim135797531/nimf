---
layout: page
title: About
---

## License

Nimf is free software: you can redistribute it and/or modify it
under the terms of the GNU Lesser General Public License as published
by the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

Nimf is distributed in the hope that it will be useful, but
WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
See the GNU Lesser General Public License for more details.

You should have received a copy of the GNU Lesser General Public License
along with this program;  If not, see <http://www.gnu.org/licenses/>.

## Architecture

```
 +- im modules --+       +-- each process ---+   +- a process --+
 | gtk im module |       |  nimf-indicator   |   |   X server   |
 | qt  im module |       +-------------------+   +--------------+
 +---------------+                |                    ^ |
         | calls                  | calls              | |
+-----------------+      +--------------------+        | |
| nimf IM library |      | nimf agent library |        | | communicates
+-----------------+      +--------------------+        | |
        ^ |                      ^ |                   | |
        | |   communicates       | |                   | |
        | |   via Unix Socket    | |                   | |
        | v                      | v                   | v
     +---------------------- a process ----------------------+
     |               nimf-daemon (including XIM)             |
     +-------------------------------------------------------+
                     | calls                  | create instance
                     | an instance            | (not module yet)
           +---------------+            +------------------+
           | engine module |   calls    | candidate module |
           |   interface   | ---------> |    interface     |
           +---------------+            +------------------+
             | (alphabetically listed)    |
             +- nimf-anthy                +- nimf-candidate (gtk3)
             +- nimf-chewing
             +- nimf-libhangul
             +- nimf-rime
             +- nimf-sunpinyin
```

## Lightweight

Nimf works as a **singleton** mode which reduces memory usage.
If you need, nimf can work as a multiple-instance mode.
The `nimf-daemon` handles both Nimf protocol and XIM protocol.
