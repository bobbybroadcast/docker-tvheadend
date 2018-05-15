This is a mostly clone of LINUX|SERVER.IO's TVHeadend version 4.3 patched with [Robert Cameron's ATSC/CableCARD](https://tvheadend.org/boards/5/topics/32813). While the 4.2 branch used TVHeadend's repo and applied patches to that repo, this release uses Robert Cameron's repo to build the image with the patches already applied.


# Note: You must use "--net=host" if you're using something like HDHomeRun prime (due to multicast).

Example Docker run cmd:

```
docker run \
  --name=tvheadend \
  --net=host \
  -v <path to data>:/config \
  -v <path to recordings>:/recordings \
  -e PGID=<gid> -e PUID=<uid>  \
  -p 9981:9981 \
  -p 9982:9982 \
  politimuse/tvheadend-atsc-patched:4.2
```

Type 'id' in a shell to get PUID, GUID - it should be whatever user docker is run as.
