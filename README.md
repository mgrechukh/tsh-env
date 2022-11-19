~/.teleport-env/
-> config.yaml
-> envs
-> -> stz
-> -> ies
-> -> int

~/.teleport-env/config.yaml

global:
  passwordstore: ~/.passwordstore
  path: private/mgrechukh/tsh-env/teleport-%s
env:
  stz:
... can override pass path for given env
  ies:
....

--
tsh-env add [--passwordstore ..] [--path ...] <name> <link>

(Either Invite or Reset link should be accepted)

---
tsh-env login [<name1>, <name2>...]

e.g.
$ tsh-env login stz ies si

without parameters, tsh-env login iterates over envs/

---
tsh-env env <env> [command.....]

e.g.

$ tsh-env env stz tsh status 
$ tsh-env env stz tsh ls
 
$ eval $(tsh-env env stz)
(prints export TELEPORT_HOME=, to use with eval )

--
tsh-env shell stz

same as tsh-env stz bash
