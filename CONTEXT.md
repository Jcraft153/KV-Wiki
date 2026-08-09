# KV-Wiki Context

## Terms

### Datapack

A portable, installable source of adventure- or campaign-specific content that builds on KV-Wiki's generic platform capabilities. In the initial storage mode, an installed Datapack is materialized into KV-Wiki persistence while retaining its source identity and provenance.

### Datapack Installation

The local, identifiable installation of a Datapack in a KV-Wiki instance. It owns the materialized content sourced from that Datapack and supports a later clean removal or replacement without treating that content as indistinguishable from KV-Wiki-owned content.

### Backup

An explicit operation that saves the complete installation state, including administrator-made changes, into a recovery file that can later restore that state.

### Clear-down

An explicit factory-reset operation that removes all installation data and returns KV-Wiki to a clean blank-slate state. It is distinct from Backup and does not itself preserve recoverable data.

### Entry

A canonical item of wiki content implemented as one Wiki.js Page and carrying a globally stable opaque identity. An Entry is either local KV-Wiki content or belongs to one Datapack Installation; aliases and display paths are mutable navigation records, while relationships and map references target the stable Entry identity.

### Audience Area

One separately authored content area of a Wiki.js Page, classified as Widely Known, Gated, Secret, or GM Only. It is stored separately from the Page and linked through `pages.id`; a Page has at most one Area of each kind. Material requiring distinct discovery conditions is modelled as separate Pages with explicit relationships rather than multiple Areas of the same kind.

### GM Note

A single GM/Admin-only note stored in its own table and linked to a Wiki.js Page through that Page's `pages.id`. It is not an Audience Area and is fetched only for GM or Admin requests; player-facing reads never retrieve it.

### Page Revision

One immutable coherent historical state of a Wiki.js Page. A Page Revision includes the Page and all of its Audience Area states together, so restoring a revision restores the exact Page state rather than combining areas from different points in time. Normal Wiki.js direct saves make the latest state live immediately while retaining prior revisions.

### Page Structure

The revisioned authored metadata of a Page: its properties, typed relationships, and map references. It is included in every Page Revision. Aliases are excluded because they are live navigation records rather than authored content state.

### Page Body

The normal Wiki.js `pages.content` body of a Page. It is that Page's Widely Known Audience Area and uses the familiar direct-save and history workflow.

### Property Definition

A versioned, typed property definition owned by a Datapack. It defines the vocabulary and validation for properties that Pages from that Datapack may use.

### Cross-Datapack Relationship

A revisioned relationship between Pages from any local or installed Datapack source. Its type is namespaced and owned by a Datapack, which defines its semantics and compatibility; KV-Wiki provides storage, authorization, and navigation but does not guarantee compatibility between Datapacks.

### Map Reference

A revisioned Page-structure record that links a Page to a map asset or map Page, with optional coordinates, label, and presentation metadata.

### Alias

A mutable navigation record for a Page. Global aliases are preferred by default; an administrator may choose a Datapack-scoped route instead. Conflict-resolution workflow is a separate decision.
