---
layout: "vsphere"
page_title: "VMware vSphere: vsphere_virtual_machine_snapshot"
sidebar_current: "docs-vsphere-resource-virtual-machine-snapshot"
description: |-
  Provides a VMware vSphere virtual machine snapshot resource. This can be used to create and delete virtual machine's snapshot.
---

# vsphere\_virtual\_machine\_snapshot

Provides a VMware vSphere virtual machine snapshot resource. This can be used to create and
delete.

## Example Usage

```hcl
resource "vsphere_virtual_machine_snapshot" "demo1" {
  vm_uuid = "42392f34-82c2-6b34-175f-3d392afbc4f1"
  snapshot_name = "Snapshot Name"
  description = "This is Demo Snapshot"
  memory = "true"
  quiesce = "true"
  remove_children = "false" -  getting used during delete vm
  consolidate = "true"
}

```


## Argument Reference

The following arguments are supported:

For resource vsphere_virtual_machine_snapshot

* `vm_uuid` - (Required) The virtual machine uuid
* `snapshot_name` - (Required) New name for the snapshot.
* `description` - (Required) New description for the snapshot.
* `memory` - (Required) If the memory flag set to true, a dump of the internal state of the virtual machine is included in the snapshot.
* `quiesce` - (Required) If the quiesce flag set to true, and the virtual machine is powered on when the snapshot is taken, VMware Tools is used to quiesce the file system in the virtual machine.
* `remove_children` - (Optional) Flag to specify removal of the entire snapshot subtree.
* `consolidate` - (Optional) If set to true, the virtual disk associated with this snapshot will be merged with other disk if possible. Defaults to true.





