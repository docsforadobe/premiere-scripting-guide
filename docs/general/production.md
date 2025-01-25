# Production object

`app.production`

**Description**

The Production object lets ExtendScript access and manipulate productions, insert projects, create new projects and bins, and move existing Production projects to Trash.

---

## Attributes

### Production.name

`app.production.name`

**Description**

The name of the production.

**Type**

String.

---

### Production.path

`app.production.path`

**Description**

The path to the Production folder.

**Type**

String.

---

### Production.projects

`app.production.projects`

**Description**

An array of the projects containined within the Production, which are currently open. Does not include non-open projects.

**Type**

[ProjectCollection object](../collection/projectcollection.md#projectcollection), read-only.

---

## Methods

### Production.addProject()

`app.production.addProject(srcProjectPath, destProjectPath)`

**Description**

Copies a project from some other location, into the Production directory.

**Parameters**

| Argument          | Type     | Description                           |
|-------------------|----------|---------------------------------------|
| `srcProjectPath`  | `String` | A path to the source project.         |
| `destProjectPath` | `String` | A destination path for added project. |

**Returns**

Returns **true** if successful.

---

### Production.close()

`app.production.close()`

**Description**

Closes the Production, and all open projects from within that Production.

**Parameters**

None.

**Returns**

Returns **true** if successful.

---

### Production.getLocked()

`app.production.getLocked(project)`

**Description**

Returns the lock state of a single project within the Production.

**Parameters**

| Argument   | Type             | Description   |
|------------|------------------|---------------|
| `project`  | `Project object` | The project   |

**Returns**

Returns **true** if the Project is locked, **false** if the Project is unlocked.

---

### Production.moveToTrash()

`app.production.moveToTrash(projectOrFolderPath, suppressUI, saveProject)`

**Description**

Moves the specified path ("bin") or .prproj into the Production's Trash folder.

**Parameters**

| Argument              | Type      | Description                                  |
|-----------------------|-----------|----------------------------------------------|
| `projectOrFolderPath` | `String`  | A path to the source project.                |
| `suppressUI`          | `Boolean` | Whether to suppress any resultant dialogues. |
| `saveProject`         | `Boolean` | Whether to save the project(s) first.        |

**Returns**

Returns **true** if successful.

---

### Production.setLocked()

`app.production.setLocked(project,locked)`

**Description**

Sets the lock state of the specified project within the Production.

**Parameters**

| Argument   | Type             | Description                              |
|------------|------------------|------------------------------------------|
| `project`  | `Project object` | The project                              |
| `locked`   | `Boolean`        | `True` for locked, `false` for unlocked. |

**Returns**

Returns **true** if successful.
