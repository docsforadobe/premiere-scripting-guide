# Component object

`app.project.sequences[index].audioTracks[index].clips[index].components[index]`

`app.project.sequences[index].videoTracks[index].clips[index].components[index]`


#### Description

The Component object represents something which has been added or applied to a trackItem.

---

## Attributes

### Component.displayName

`app.project.sequences[index].audioTracks[index].clips[index].components[index].displayName`

`app.project.sequences[index].videoTracks[index].clips[index].components[index].displayName`


#### Description

The name of the component, as it is displayed to the user. Localized.

#### Type

String; read-only.

---

### Component.matchName

`app.project.sequences[index].audioTracks[index].clips[index].components[index].matchName`

`app.project.sequences[index].videoTracks[index].clips[index].components[index].matchName`


#### Description

The name of the component, as it is loaded from disk; used to uniquely identify effect plug-ins.

#### Type

String; read-only.

---

### Component.properties

`app.project.sequences[index].audioTracks[index].clips[index].components[index].properties`

`app.project.sequences[index].videoTracks[index].clips[index].components[index].properties`


#### Description

The properties of the component in question; typically, these are effect parameters.

#### Type

Array of components, read-only; (ComponentParamCollection object).
