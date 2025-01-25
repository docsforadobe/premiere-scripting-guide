# Component object

`app.project.sequences[index].audioTracks[index].clips[index].components[index]`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].components[index]`
<br/>

**Description**

The **component** object represents something which has been added or applied to a trackItem.

---

## Attributes

### Component.displayName

`app.project.sequences[index].audioTracks[index].clips[index].components[index].displayName`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].components[index].displayName`
<br/>

**Description**

The name of the component, as it is displayed to the user. Localized.

**Type**

String; read-only.

---

### Component.matchName

`app.project.sequences[index].audioTracks[index].clips[index].components[index].matchName`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].components[index].matchName`
<br/>

**Description**

The name of the component, as it is loaded from disk; used to uniquely identify effect plug-ins.

**Type**

String; read-only.

---

### Component.properties

`app.project.sequences[index].audioTracks[index].clips[index].components[index].properties`
<br/>
`app.project.sequences[index].videoTracks[index].clips[index].components[index].properties`
<br/>

**Description**

The properties of the component in question; typically, these are effect parameters.

**Type**

Array of components, read-only; (ComponentParamCollection object).
