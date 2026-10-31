# lazylibrarian-swarm

Portainer stack `lazylibrarian-swarm` on ore-dock-110-1, git-backed with
auto-update every 15 minutes.

Scheduled onto the swarm manager node (`node.role==manager`), matching the
sibling book stacks (beets, calibre, readarr).

The original compose carried a placement constraint on a node label
(`deployment.target.lazylib`) that is set on NO node in this swarm, so the
service could never schedule. The constraint was changed to
`node.role==manager`, which is where every other media/book stack runs.
