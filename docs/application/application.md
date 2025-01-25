<a id="application"></a>

# Application object

`app`

**Description**

Provides access to objects and application settings within Premiere Pro.
The single global object is always available by its name, **app**.

---

## Attributes

<a id="app-anywhere"></a>

### app.anywhere

`app.anywhere`

**Description**

An [Anywhere object](../general/anywhere.md#anywhere), providing access to available Anywhere servers. Only available when running in Anywhere configuration (discontinued).

**Type**

[Anywhere object](../general/anywhere.md#anywhere).

---

<a id="app-build"></a>

### app.build

`app.build`

**Description**

The number of the build of Premiere Pro being run.

**Type**

String; read-only.

**Example**

Get a build version of current application  *(Adobe Premiere Pro version 14.3.1 (Build 45))*

```javascript
parseInt(app.build); // 45
```

---

<a id="app-encoder"></a>

### app.encoder

`app.encoder`

**Description**

Provides access to Adobe Media Encoder (on the same system).

Warning: app.encoder is broken on Premiere Pro 14.3.1 - 15 on Mac only. Fixed in 22 and up.
[https://community.adobe.com/t5/premiere-pro-discussions/missing-the-object-app-encoder-14-3-1-15-0-15-1-15-2/m-p/12544488](https://community.adobe.com/t5/premiere-pro-discussions/missing-the-object-app-encoder-14-3-1-15-0-15-1-15-2/m-p/12544488)

**Type**

[Encoder object](../general/encoder.md#encoder).

---

<a id="app-getappprefpath"></a>

### app.getAppPrefPath

`app.getAppPrefPath`

**Description**

The path containing the currently active “Adobe Premiere Pro Prefs” file.

**Type**

String; read-only.

**Example**

Get a path to a currently active preference file

```javascript
app.getAppPrefPath; // /Users/USERNAME/Documents/Adobe/Premiere Pro/14.0/Profile-USERNAME/
```

---

<a id="app-getappsystemprefpath"></a>

### app.getAppSystemPrefPath

`app.getAppSystemPrefPath`

**Description**

Premiere Pro’s active configuration files, not specific to a given user.

**Type**

String; read-only.

**Example**

Get a path to a currently active configuration folder

```javascript
app.getAppSystemPrefPath; // /Library/Application Support/Adobe/Adobe Premiere Pro 2020/
```

---

<a id="app-getpproprefpath"></a>

### app.getPProPrefPath

`app.getPProPrefPath`

**Description**

The path containing the currently active “Adobe Premiere Pro Prefs” file.

**Type**

String; read-only.

**Example**

Get a path to a currently active preference file

```javascript
app.getPProPrefPath; // /Users/USERNAME/Documents/Adobe/Premiere Pro/14.0/Profile-USERNAME/
```

---

<a id="app-getpprosystemprefpath"></a>

### app.getPProSystemPrefPath

`app.getPProSystemPrefPath`

**Description**

Premiere Pro’s active configuration files, not specific to a given user.

**Type**

String; read-only.

**Example**

Get a path to a currently active configuration folder

```javascript
app.getPProSystemPrefPath; // /Library/Application Support/Adobe/Adobe Premiere Pro 2020/
```

---

<a id="app-learnpanelcontentdirpath"></a>

### app.learnPanelContentDirPath

`app.learnPanelContentDirPath`

**Description**

Get the Learn panel’s contents directory path.

**Type**

String; read-only.

**Example**

Get a path to a Learn panel’s directory

```javascript
app.learnPanelContentDirPath; // /Users/Shared/Adobe/Premiere Pro 2020/Learn Panel/
```

---

<a id="app-learnpanelexampleprojectdirpath"></a>

### app.learnPanelExampleProjectDirPath

`app.learnPanelExampleProjectDirPath`

**Description**

Get the Learn panel’s example projects directory path.

**Type**

String; read-only.

**Example**

Get a path to a Learn panel’s example projects’ directory

```javascript
app.learnPanelExampleProjectDirPath; // /Users/Shared/Adobe/Premiere Pro/14.0/Tutorial/Going Home project/
```

---

<a id="app-metadata"></a>

### app.metadata

`app.metadata`

**Description**

Get applications Metadata object.

**Type**

[Metadata object](../general/metadata.md#metadata), read-only.

---

<a id="app-path"></a>

### app.path

`app.path`

**Description**

Get a path to applications executable file.

**Type**

String; read-only.

**Example**

Get a path to applications executable file.

```javascript
app.path; // /Applications/Adobe Premiere Pro 2020/Adobe Premiere Pro 2020.app/
```

---

<a id="app-production"></a>

### app.production

`app.production`

**Description**

The currently active production.

**Type**

[Production object](../general/production.md#production) if at least 1 production is open, `null` otherwise.

---

<a id="app-project"></a>

### app.project

`app.project`

**Description**

The currently active project.

**Type**

[Project object](../general/project.md#project).

---

<a id="app-projectmanager"></a>

### app.projectManager

`app.projectManager`

**Description**

Provides access to project management functions within Premiere Pro.

**Type**

[ProjectManager object](../general/projectmanager.md#projectmanager).

---

<a id="app-projects"></a>

### app.projects

`app.projects`

**Description**

An array referencing all open projects; `numProjects` contains size.

**Type**

[ProjectCollection object](../collection/projectcollection.md#projectcollection), read-only.

---

<a id="app-properties"></a>

### app.properties

`app.properties`

**Description**

The properties object provides methods to access and modify preference values.

**Type**

[Properties object](../general/properties.md#properties), read-only;

---

<a id="app-sourcemonitor"></a>

### app.sourceMonitor

`app.sourceMonitor`

**Description**

Provides access to [SourceMonitor object](../general/sourcemonitor.md#sourcemonitor).

**Type**

[SourceMonitor object](../general/sourcemonitor.md#sourcemonitor).

---

<a id="app-userguid"></a>

### app.userGuid

`app.userGuid`

**Description**

A unique identifier for the currently logged-in Creative Cloud user.

**Type**

String; read-only.

---

<a id="app-version"></a>

### app.version

`app.version`

**Description**

The version of Premiere Pro, providing the API.

**Type**

String; read-only.

**Example**

Get a version of a current application  *(Adobe Premiere Pro version 14.3.1 (Build 45))*

```javascript
app.version; // 14.3.1
```

---

## Methods

<a id="app-enableqe"></a>

### app.enableQE()

`app.enableQE()`

**Description**

Enables Premiere Pro’s QE DOM.

**Parameters**

None.

**Returns**

Returns true if QE DOM was enabled.

---

<a id="app-getenableproxies"></a>

### app.getEnableProxies()

`app.getEnableProxies()`

**Description**

Determines whether proxy usage is currently enabled.

**Parameters**

None.

**Returns**

Returns 1 if proxies are enabled, 0 of they are not.

---

<a id="app-getworkspaces"></a>

### app.getWorkspaces()

`app.getWorkspaces()`

**Description**

Obtains an array of available workspaces as Strings.

**Parameters**

None.

**Returns**

`Array` if successful, `null` if unsuccessful.

**Example**

Get a list of available workspaces.

```javascript
app.getWorkspaces();
/* [
    "All Panels",
    "Assembly",
    "Audio",
    "Color",
    "Editing",
    "Effects",
    "Graphics",
    "Learning",
    "Libraries",
    "Metalogging",
    "Production"
]; */
```

---

<a id="app-isdocument"></a>

### app.isDocument()

`app.isDocument(path)`

**Description**

Determines whether the file at path can be opened as a Premiere Pro [project](../general/project.md#project).

**Parameters**

| Argument   | Type     | Description       |
|------------|----------|-------------------|
| `path`     | `String` | A path to a file. |

**Returns**

Returns **true** if file can be opened as a Premiere Pro [project](../general/project.md#project).

**Example**

Test for valid project files

```javascript
app.isDocument('~/Desktop/myProject.prproj'); // true
app.isDocument('~/Desktop/textFile.txt');     // false
app.isDocument('~/Desktop/footageFile.mov');  // false
app.isDocument('~/Desktop/imageFile.mov');    // false
```

---

<a id="app-isdocumentopen"></a>

### app.isDocumentOpen()

`app.isDocumentOpen()`

**Description**

Determines whether there are any [projects](../general/project.md#project) currently open.

**Parameters**

None.

**Returns**

Returns **true** if at least 1 project is open; otherwise **false**.

---

<a id="app-newproject"></a>

### app.newProject()

`app.newProject(path)`

**Description**

Creates a new .prproj [Project object](../general/project.md#project), at the specified path.

**Parameters**

| Argument   | Type     | Description                                                          |
|------------|----------|----------------------------------------------------------------------|
| `path`     | `String` | A full path to new project; a .prproj extension will *not* be added. |

**Returns**

Returns **true** if successful.

---

<a id="app-opendocument"></a>

### app.openDocument()

`app.openDocument(path)`

**Description**

Opens the file at the specified path, as a Premiere Pro [Project object](../general/project.md#project).

**Parameters**

| Argument                   | Type      | Description                                                     |
|----------------------------|-----------|-----------------------------------------------------------------|
| `path`                     | `String`  | Full path to the document to be opened.                         |
| `suppressConversionDialog` | `Boolean` | Optional. Suppress project conversion dialog.                   |
| `bypassLocateFileDialog`   | `Boolean` | Optional. Bypass the locate file dialog.                        |
| `bypassWarningDialog`      | `Boolean` | Optional. Bypass warning dialog.                                |
| `doNotAddToMRUList`        | `Boolean` | Optional. Skip adding this file to the Most Recently Used List. |

**Returns**

Returns **true** if file was successfully opened.

---

<a id="app-openfcpxml"></a>

### app.openFCPXML()

`app.openFCPXML(path, projPath)`

**Description**

Opens an FCP XML file as a Premiere Pro [Project object](../general/project.md#project) (specified in projPath).

**Parameters**

| Argument   | Type     | Description   |
|------------|----------|---------------|
| `path`     | `String` |               |
| `projPath` | `String` |               |

**Returns**

Returns **true** if file was successfully opened as a Premiere Pro [Project object](../general/project.md#project).

---

<a id="app-quit"></a>

### app.quit()

`app.quit()`

**Description**

Quits Premiere Pro; user will be prompted to save any changes to [Project object](../general/project.md#project).

**Parameters**

None.

**Returns**

Nothing.

---

<a id="app-setenableproxies"></a>

### app.setEnableProxies()

`app.setEnableProxies(enabled)`

**Description**

Determines whether proxy usage is currently enabled.

**Parameters**

| Argument   | Type      | Description                               |
|------------|-----------|-------------------------------------------|
| `enabled`  | `Integer` | `1` turns proxies on, `0` turns them off. |

**Returns**

Returns 1 if proxy enablement was changed.

---

<a id="app-setextensionpersistent"></a>

### app.setExtensionPersistent()

`app.setExtensionPersistent(extensionID, persistent)`

**Description**

Whether extension with the given extensionID persists, within this session.

**Parameters**

| Argument      | Type      | Description                                                   |
|---------------|-----------|---------------------------------------------------------------|
| `extensionID` | `String`  | Which extension to modify.                                    |
| `persistent`  | `Integer` | Pass `1` to keep extension in memory, `0` to allow unloading. |

**Returns**

Returns **true** if successful.

**Example**

```javascript
var extensionID = 'com.adobe.PProPanel';
// 0 - while testing (to enable rapid reload);
// 1 - for "Never unload me, even when not visible."
var persistent = 0;

app.setExtensionPersistent(extensionID, persistent);
```

---

<a id="app-setscratchdiskpath"></a>

### app.setScratchDiskPath()

`app.setScratchDiskPath(path, scratchDiskType)`

**Description**

Specifies the path to be used for one of Premiere Pro’s scratch disk paths.

**Parameters**

| Argument          | Type     | Description                                                                                                                                                                                                                                                                                                                                                                                     |
|-------------------|----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `path`            | `String` | The new path to be used.                                                                                                                                                                                                                                                                                                                                                                        |
| `scratchDiskType` | `Enum`   | Enumerated value, must be one of the following:<br/><br/>- `ScratchDiskType.FirstVideoCaptureFolder`<br/>- `ScratchDiskType.FirstAudioCaptureFolder`<br/>- `ScratchDiskType.FirstVideoPreviewFolder`<br/>- `ScratchDiskType.FirstAudioPreviewFolder`<br/>- `ScratchDiskType.FirstAutoSaveFolder`<br/>- `ScratchDiskType.FirstCCLibrariesFolder`<br/>- `ScratchDiskType.FirstCapsuleMediaFolder` |

**Returns**

Returns ‘true’ if successful.

**Example**

```javascript
var scratchPath = Folder.selectDialog('Choose new scratch disk folder');
if (scratchPath && scratchPath.exists) {
    app.setScratchDiskPath(scratchPath.fsName, ScratchDiskType.FirstAutoSaveFolder);
}
```

---

<a id="app-setsdkeventmessage"></a>

### app.setSDKEventMessage()

`app.setSDKEventMessage(message, decorator)`

**Description**

Writes a string to Premiere Pro’s Events panel.

**Parameters**

| Argument    | Type     | Description                                                                                |
|-------------|----------|--------------------------------------------------------------------------------------------|
| `message`   | `String` | A message to display.                                                                      |
| `decorator` | `String` | Decorator, one of:<br/><br/>`info`<br/><br/><br/>`warning`<br/><br/><br/>`error`<br/><br/> |

**Returns**

Returns ‘true’ if successful.

---

<a id="app-setworkspace"></a>

### app.setWorkspace()

`app.setWorkspace(workspace)`

**Description**

Set workspace as active. Use [app.getWorkspaces()](#app-getworkspaces) to get a list of all available workspaces.

**Parameters**

| Argument    | Type     | Description                |
|-------------|----------|----------------------------|
| `workspace` | `String` | The name of the workspace. |

**Returns**

`Boolean`.

**Example**

Activate `Editing` workspace.

```javascript
var workspace = 'Editing';
if (app.setWorkspace(workspace)) {
    alert('Workspace changed to "' + workspace + '"');
} else {
    alert('Could not set "' + workspace + '" workspace');
}
```

---

<a id="app-trace"></a>

### app.trace()

`app.trace()`

**Description**

Writes a string to Premiere Pro’s debug console.

**Parameters**

None.

**Returns**

Returns **true** if trace was added.

---

<a id="app-getprojectviewids"></a>

### app.getProjectViewIDs()

`app.getProjectViewIDs()`

**Description**

Returns the view IDs of currently-open views, associated with any project.

**Parameters**

None.

**Returns**

An array of view IDs; can be null.

**Example**

```javascript
var allViewIDs = app.getProjectViewIDs();
if (allViewIDs){
    var firstOne = allViewIDs[0];
} else {
    // No views open.
}
```

---

<a id="app-getprojectfromviewid"></a>

### app.getProjectFromViewID()

`app.getProjectFromViewID()`

**Description**

Returns the Project associated with the provided View ID.

**Parameters**

A View ID, obtained from `getProjectViewIDs`.

**Returns**

A Project object, for the project associated with the provided View ID. Can be `null`.

**Example**

```javascript
var allViewIDs = app.getProjectViewIDs();
if (allViewIDs){
    var firstOne = allViewIDs[0];
    if (firstOne){
        var thisProject = getProjectFromViewID(firstOne);
        if (thisProject){
            var name = thisProject.name;
        } else {
            // no project associated with that view ID.
        }
} else {
    // No views open.
}
```

---

<a id="app-getcurrentprojectviewselection"></a>

### app.getCurrentProjectViewSelection()

`app.getCurrentProjectViewSelection()`

**Description**

Returns an array of projectItems selected, in the current active project view.

**Parameters**

None.

**Returns**

An array of projectItems; can be null.

**Example**

```javascript
var selectedItems = app.getCurrentProjectViewSelection();
if (selectedItems){
    var firstOne = selectedItems[0];
} else {
    // No projectItems selected.
}
```
