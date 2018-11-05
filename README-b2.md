# B2 Alpine Specifics
This is simply a fork of the official Alpine linux repository used to create the images that land on Docker hub. We use this fork to ensure images running on our cluster are built from a known, signed source. The only modifications made support tagging images unique to our registry.

## Updating
1. Make sure you have added the upstream repo.
```
git remote add upstream https://github.com/gliderlabs/docker-alpine.git
```
2. Fetch the upstream.
```
git fetch upstream
```
3. Merge the upstream to master.
```
git merge upstream/master
```
4. Push the changes to this repo.
```
git push
```

## Building
Use the existing build script with a pointer to the appropriate options file. As of this writing the `x86_64` build of `3.6`, `3.7`, and `3.8` have been updated to tag the image with the appropriate `registry2` tag. Note that on OSX (at least) you must run the build script as sudo or it will fail.

Example:
```
[mattbrewster@mbp ~/dev/docker-alpine (master *)]$ sudo ./build versions/library-3.6/x86_64/options 
```

Once built, use the normal pushing process documented in the Internal Devops repo.

## Repos
The B2 Alpine repo is located at `registry2.base2d.com/ops/alpine`.
