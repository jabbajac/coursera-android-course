## Lab One Writeup
### Jack Yuan

---


### 7.2 Telnet

#### Timings

3G - 7s
EDGE - 24s

3G - 5S
EDGE - 20s

3G - 6S
EDGE - 25s

3G - 6s
EDGE - 23s

3G - 4s
EDGE - 22s

Average load time 3G: 5.6s
Average load time EDGE: 22.8s

The emulator does affect the network speed. On EDGE the emulator will bandwidth limit the virtual device to simulate a slower network.

### 7.5 Hierarchy View Tool

<dl>
    <dt>26.a.</dt>
    <dd> The View tree has 9 levels </dd>

    <dt>26.b.</dt>
    <dd> The parent is a LinearLayout. It's parent contains 3 children. THe plus button has a relative index of 2.</dd>
</dl>

### 7.6 DeskClock

<dl>
    <dt>27.b</dt>
    <dd>
Activity - DeskClocks
	<activity android:name="DeskClock"
                android:label="@string/app_label"
                android:theme="@style/DeskClock"
                android:icon="@mipmap/ic_launcher_alarmclock"
                android:launchMode="singleTask"
                >
Services - AlarmKlaxon
	<service android:name="AlarmKlaxon"
                android:exported="false"
                android:description="@string/alarm_klaxon_service_desc">
            <intent-filter>
                <action android:name="com.android.deskclock.ALARM_ALERT" />
            </intent-filter>
        </service>
Content Providers - AlarmProvider
	<provider android:name="AlarmProvider"
                android:authorities="com.android.deskclock"
                android:exported="false" />
Broadcast Recievers - AlarmReceiver
	<receiver android:name="AlarmReceiver"
                android:exported="false">
            <intent-filter>
                <action android:name="com.android.deskclock.ALARM_ALERT" />
                <action android:name="alarm_killed" />
                <action android:name="cancel_snooze" />
            </intent-filter>
        </receiver>
    </dd>
    <dt>27.c</dt>
    <dd>3 layout directories:
      * layout - for phones
      * layout-land - for phones in landscape mode
      * layout-sw600dp - for tablets
    </dd>
    <dt>27.d</dt> 
    <dd>There are 56 values directories. Two strings that can be configured for different languages are "alert" and "ringtone"</dd> 
    <dt>27.e</dt> 
    <dd>cities is referenced in the onCreateView method of ClockFragment as a parameter for findViewByID
</dl>

### 7.7 Logcat

<dl>
    <dt>28.b</dt> 
    <dd>The log tag used by the application's main Activity is WikiNotes. In the application's source code there is a line in WikiNotes.java, `private static final String TAG = "WikiNotes"`
    </dd> 
    <dt>28.c</dt> 
    <dd> The message associated with the first log entry emitted when the application starts runnign is "Exiting onCreate()"
    </dd>
</dl>

### 7.8 Heap View

<dl>
    <dt>29.b</dt>
      <dd>47,035 objects have been created</dd>
    <dt>29.c</dt>
      <dd>Data object was allocated most frequently</dd>
    <dt>29.d</dt>
      <dd>889.586 KB of memory has been allocated for this type of Object</dd>
</dl>

### 7.9 Method Profiling

<dl>
    <dt>30.b</dt>
      <dd>showWikiNote</dd>
    <dt>30.c</dt> 
      <dd>WikiNotes.java</dd>
    <dt>30.d</dt> 
      <dd>
      inclusive real time -351.741
      exclusive real time - 0.516
      Exclusive real time is time spent in the method alone, not counting the time spent in functions called from this method. Inclusive includes the times spend in functions called from this method. 
    </dd>
</dl>

### 7.10 Debugging and JUnit Testing

<dl> 
    <dt>35.a</dt>
      <dd>Before line 94, mathResult did not exist. At line 94 mathResult is set to `result.getText().toString(). After line 94, mathResult has a value of "96".</dd>
    <dt>35.b</dt>
      <dd>Since SimpleCalc does not allow the creation of negative numbers so NUMBER_NEG_22 actually is only 22. Since we added the values together 22 and 74 give 96. The intention was to try and get 52 but due to the limitations of SimpleCalc, that was not accomplished. Whether or not the value is a correct value depends on one's interpretation of whether correct is having the answer match the intended answer or correct is the function properly executing what it is supposed to do. Since SimpleCalc only saw 22 and not -22 one can argue that SimpleCalc is correct in show ing a result of 96.</dd>
</dl>
