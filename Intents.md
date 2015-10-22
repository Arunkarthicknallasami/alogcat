aLogcat accepts the following intents,

## org.jtb.alogcat.intent.START ##

This starts the application. Intent must be broadcast with the "single top" for it to effect an already running copy of aLogcat.

The following extras are supported,

### FILTER ###

Sets aLogcat's filter value. Value is interpreted as a string if substring filter mode is in effect, or as a regular expression otherwise. Again, the regular expression string value must be Java conforming (it needs to be properly escaped).

Note in all cases, extras that effect aLogcat's preferences are persistent. That is, if you start aLogcat with intent START and pass a filter extra, the filter value lives beyond the life cycle of this particular application invocation. I.e., it acts as if you had changed the filter value from aLogcat's preferences.

### LEVEL ###

Sets aLogcat's level. Value can be one of: V, D, I, W, or E.

## org.jtb.alogcat.intent.SAVE ##

Triggers aLogcat to immediately write a log snapshot to /sdcard/alogcat. This intent accepts the same extras a the START intent, with the same semantics.

## org.jtb.alogcat.intent.SHARE ##

Triggers aLogcat to share the state of the current log, as if menu > share was selected from the application. This intent accepts the same extras a the START intent, with the same semantics.


## org.jtb.alogcat.intent.SAVE\_START ##

Triggers aLogcat to begin periodically saving log snapshots to /sdcard/alogcat. In addition to the extras allows by the START intent, this intent allows,

### FREQUENCY ###

The frequency to save log snapshots. Value must be one of,

```
FIFTEEN_MINUTES
HALF_HOUR
HOUR
```

## org.jtb.alogcat.intent.SAVE\_STOP ##

Triggers aLogcat to stop periodically saving log snapshots to /sdcard/alogcat.