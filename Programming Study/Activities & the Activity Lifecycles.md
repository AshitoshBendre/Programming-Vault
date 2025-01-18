

### What Are Activities?

- Activities are a key component of Android apps. They represent a single screen with a user interface and serve as an entry point for user interaction
-  They manage the UI and handle user actions, acting as a bridge between the user and the app's logic.
- Activities are managed by the Activity Manger, which handles their state transitions.

### Why are Activity Lifecycles Important

- The **Activity Lifecycle** allows developers to manage the transitions between different states of the app. This is critical for ensuring proper resource usage, saving app state, and handling interruptions like phone calls or app minimization.

### Activity Lifecycle Methods

1. **`onCreate()`**
- **Called** : When the activity is created for the first time.
- **Purpose** :  Initialize the UI components, set up data binding, initialize logic.
- **Example** : 
``` 
override fun onCreate(savedInstanceState: Bundle?) {
    super.onCreate(savedInstanceState)
    setContentView(R.layout.activity_main)
    // Initialize UI and logic
}
```

2. **`onStart()`**
	 
- **Called** : When the activity becomes visible to the user.
- **Purpose** : Start animations, UI updates, or any logic that needs the app to be visible
- **Example** :
```
override fun onStart() {
    super.onStart()
    // App is visible but not interactive
}

```

3. **`onResume()`**

- **Called :** When the activity starts interacting with the user.
- **Purpose :** Resume ongoing tasks like animations or media playback.
- **Example :**
```
override fun onResume() {
    super.onResume()
    // App is in the foreground and interactive
}
```

4. **`onPause()`**

- **Called :** When the activity is partially obscured (e.g., a dialog appears or the user switches to another app).
- **Purpose :** Pause heavy operations or release resources that don’t need to run in the background.
- **Example :**
``` 
override fun onPause() {
    super.onPause()
    // Pause ongoing tasks like media playback
}

```

5. **`onStop()`**

- **Called :** When the activity is no longer visible.
- **Purpose :** Release resources, stop services, or save data.
- **Example :**
```
override fun onStop() {
    super.onStop()
    // Clean up resources
}
	
```

6. **`onDestroy()`**

- **Called :** When the activity is being destroyed, either by the user explicitly or by the system to reclaim resources.
- **Purpose :** Final cleanup of resources, release memory, or close databases.
- **Example :** 
```
override fun onDestroy() {
    super.onDestroy()
    // Final cleanup
}

```

7. **`onRestart()`**

- **Called:** When the activity is stopped and then started again.
- **Purpose:** Prepare the activity to resume from its stopped state.
- Example:
```
override fun onRestart() {
    super.onRestart()
    // App is restarting after being stopped
}

```

### **Visualizing the Lifecycle**

The activity lifecycle can be visualized as a state diagram:

- **Active States:**
    - **`onCreate()` -> `onStart()` -> `onResume()`**
- **Paused/Stopped States:**
    - **`onPause()` -> `onStop()`**
- **Restarted/Destroyed States:**
    - **`onRestart()` -> `onStart()` (Restarted)**
    - **`onDestroy()` (Destroyed)**


### **Additional Topics to Learn (This is created by Ai)**

1. **Configuration Changes**
    
    - Handle changes like screen rotation by overriding `onConfigurationChanged()` or using a `ViewModel` for data persistence.
    - Learn about saving and restoring the activity state with `onSaveInstanceState()` and `onRestoreInstanceState()`.
2. **Multiple Activities**
    
    - An app can have multiple activities for different screens (e.g., LoginActivity, SettingsActivity).
    - Use **Intents** to navigate between activities.
3. **Fragments**
    
    - Learn about fragments, which allow modular UI and reusable components within activities.
4. **ViewModel and Lifecycle Observers**
    
    - Use `ViewModel` and `LiveData` to persist data across configuration changes.
    - Implement `LifecycleObserver` for better lifecycle management.
5. **Launch Modes and Task Management**
    
    - Understand launch modes (`standard`, `singleTop`, `singleTask`, `singleInstance`) and their effects on activity stack behavior.
6. **Background and Foreground**
    
    - Learn how the lifecycle interacts with Android's **App Lifecycle** (foreground and background states).