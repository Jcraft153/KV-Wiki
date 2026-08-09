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
