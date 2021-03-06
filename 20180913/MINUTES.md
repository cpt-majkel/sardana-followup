# Sardana Follow-up Meeting on 2018/09/13

## 1. Presentation

Release process summary and ideas

- More automatization of the release process.
- Simplify process
- Rotative process. Next release done by Teresa or Antonio with help/guidance of Grzegorz or Zibi.
- Project Dashboard on Github are very useful.
- Next Release on January/February.
- [How to Release](https://github.com/sardana-org/sardana/blob/develop/doc/how_to_release.md)

## 2. User Experience Report

- Alba:
  - Lack of documentation about Hooks
  - General Scan or Acquisition workflows are not documented
  - Validation of Environment Variables.
- Solaris:
  - Moving a motor with umv (or any macro that updates the output) and cancel the movement, spock will give you a traceback. (Polling involved on some attributes)
- Desy:
  - Change to Debian 9, new Taurus and Sardana
  - Move a motor and atk panel doesn't update the position. Client don't get events.
  - After ctrl+C MacroServer doesn't work anymore.
  - Issue with the behavior of the General Stop Function.
  - IPython problem with the prompt.
- Max IV:
  - Being able to combine experimental channels from 2 Pools and 2 MacroServers

## 3. Collaborative Developments

- Spock syntax. PR as WIP to improve the parser
- General Stop Function. Check if there is an issue for this one or create a new one. (issue #202)
- Logstash handler asynchronous behavior

## 4. New Developments, Enhancements or Bug Fixes

- Optional parameters allowed
- Exp Conf Widget to refresh on Events, close to be integrated
- LogStash issue consuming messages

## 5. Pending PR distribution

- #420: DummyMotorController. [Stalled]
- #579: Fix error with case sensitivity. [Stalled]
- #671: Synchronization Parameters - Assigned to Zbigniew
- #672: Combined with #777 and #781
- #675: [Stalled]
- #689: WIP
- #695: WIP  
- #764: Assigned to Zbigniew
- #777: Zbigniew, Teresa and Grzegorz to work on it
- #782: Assign to Antonio. (Idea: have a general logging of hooks)
- #816: Assign to Grzegorz

Pending to be reviewed:

- #867:
- #882:
- #908:
- #924:
- #926:
- #936:

## 6. AOB

- Sardana Documentation Camp Summary (slides from Zbigniew):
  - Sardana Training materials
  - Outdated documentation was mixed with the up to date documentation
  - How to install Sardana and its dependencies on Windows is not clear
  - How to integrate real hardware with Sardana? Simple recommendations. TODO.
- Brainstorming on how to improve and organize work
  - Move to 4th of Oct.
- NoBugs 2018?
- Find another tool for video-conference
