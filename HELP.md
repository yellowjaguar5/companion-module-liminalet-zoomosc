## ZoomOSC

More information at: <a href='https://www.liminalet.com/zoomosc' target='_new'>liminalet.com/zoomosc</a>

**Config**  
Specify IP and port for send and receive to ZoomOSC

**Suggested Default Port & IP Setup**

Note: We recommend using the default port numbers below to get started, but other open ports may be used.
* ZoomOSC Configuration (**ZoomOSC Pro Reccomended** for full functionality, but not required):
  * ZoomOSC Transmission IP: Device with Companion
  * ZoomOSC Transmission port: 1234
  * ZoomOSC Receive port: 9090
* Companion Module Configuration:
  * Companion Instance: Target IP: Device with ZoomOSC
  * Companion Instance: Target port: 9090
  * Companion Instance: Receive port: 1234


**User Variables**
* Once subscribed, user variables will be populated as:
 $(INSTANCE:[VARIABLENAME]_[USERSOURCE])
 * examples:(we want to return the Video Status of our user called Alice, with a Target ID of 0, Gallery Index of 0 and Gallery Position of 0,0)
  * Targeting by username ('alice')
    * $(zoomosc:vidStatus_user_alice)
  * Targeting by Target ID (0)
    * $(zoomosc:vidStatus_tgtID_0)
  * Targeting by Gallery Index ('0')
    * $(zoomosc:vidStatus_galInd_0)
  * Targeting by Gallery Position ('0,0')
    * $(zoomosc:vidStatus_galPos_0,0)
  * Targeting by List Index (0)
    * $(zoomosc:videoStatus_listIndex_0)
  * Targeting by Selection Group (available for actions only)

  * **Available User Variables**
    * User Name             : userName             | example: $(zoomosc:userName_alice)
    * Gallery Index         : galIndex             | example: $(zoomosc:galIndex_alice)
    * Role                  : role                 | example: $(zoomosc:role_alice)
    * Online status         : onlineStatus         | example: $(zoomosc:onlineStatus_alice)
    * Video Status          : videoStatus          | example: $(zoomosc:vidStatus_alice)
    * Audio Status          : audioStatus          | example: $(zoomosc:audioStatus_alice)
    * Hand Status           : handStatus           | example: $(zoomosc:handStatus_alice)
    * Active Speaker Status : activeSpeaker        | example: $(zoomosc:active_speaker_alice)


**Client Variables**

  * **Available Client Variables**
    * ZoomOSC Version        : zoomOSCVersion      | $(zoomosc:client_zoomOSCVersion)
    * Subscribe Mode         : subscribeMode       | $(zoomosc:client_subscribeMode)    
    * Gallery Track Mode     : galTrackMode        | $(zoomosc:client_galTrackMode)
    * Call Status            : callStatus          | $(zoomosc:client_callStatus)
    * Number of Targets      : numberOfTargets     | $(zoomosc:client_numberOfTargets)
    * Number of Users in Call: numberOfUsersInCall | $(zoomosc:client_numberOfUsersInCall)
    * Active Speaker         : activeSpeaker       | $(zoomosc:client_activeSpeaker)

**Actions**

* **Pins**
  * Pin Screen 1
  * Add Pin Screen 1
  * Un-Pin Screen 1
  * Clear pinned Screen 1
  * Pin Screen 2
  * Add Pin Screen 2
  * Un-Pin Screen 2
  * Clear Pinned Screen 2
* **Remote Pins**
  * Pin Screen 1 on remote client
  * Add Pin Screen 1 on remote client
  * Un-Pin Screen 1 on remote client
  * Clear Pinned Screen 1 on remote client
  * Pin Screen 2 on remote client
  * Add Pin Screen 2 on remote client
  * Un-Pin Screen 2 on remote client
  * Clear Pinned Screen 2 on remote client
* **Spotlight**
  * Spotlight User
  * Add Spotlit User
  * Un-spotlight User
  * Clear Spotlight
* **Audio/Video**
  * Video On
  * Video Off
  * Mute Audio
  * UnMute Audio
  * UnMute All
  * Enable Users UnMute
  * Disable Users UnMute
  * Mute All
* **Chat**
  * Send Chat Message
* **Remote Chat**
  * Send Chat Message from Remote User
* **Raise/Lower Hand**
  * Raise Hand
  * Lower Hand
  * Lower All Hands
* **Role Actions**
  * Make User Host
  * Make Co-Host
  * Revoke Co-Host
  * Reclaim Host
  * Make Panelist
  * Make Attendee
  * Eject User(s)
* **Screenshare Actions**
  * Start Screenshare
  * Stop Screenshare
* **App Actions**
  * Gallery View
  * Speaker View
  * Show Non Video Participants
  * Hide Non Video Participants
  * Show Usernames
  * Hide Usernames
  * Enable Original Sound
  * Disable Original Sound
* **Settings Actions**
  * List Mic Devices
  * Set Mic Devices
  * List Speaker devices
  * Set Speaker Device
  * Get Mic Volume
  * Set Mic Volume
  * Get Speaker Volume
  * Set Speaker Volume
  * List Camera Devices
  * Set Camera Device
  * List backgrounds
  * Set Background
  * List Video filters
  * Set Video Filter
  * Get Camera Device
  * Get Mic Device
  * Get Speaker Device
  * Get Background
  * Get Video Filter
* **General Local Application Actions**
  * Ping Client
  * Subscribe
  * Update
  * Include
  * Set Gallery Tracking Mode
  * Get Gallery Count
  * Load
  * Save
  * List
  * Reset
  * Leave Meeting
  * End Meeting
  * Join Meeting

**Internal Actions**
These actions are used internally to the ZoomOSC Companion plugin and only available within it.
* **Selection Actions**
  * **Note on selection group usage**
    * To perform an action on the selection group, choose `--Selection--` under the user dropdown of any ZoomOSC user action.
    * Not all user actions can target groups of users. Check the ZoomOSC Log to for any single-user-only warnings.
  * Add user to selection group
  * Remove user from selection group
  * Toggle user to/from selection group
    * Adds user to selection group if not selected.
    * Removes user from selection group if selected.
  * Clear selection group

  * **List Index Actions**
  Target a user by their position in the list of users as reported by ZoomOSC. This allows you to list all users in the call and target actions at each user.
  Using "list offset" allows a set of user indexes to be assigned (such as 0, 1, 2, 3, 4) and to "page" these users by increasing the list index to 5, meaning that index 0 will become index 5 etc
