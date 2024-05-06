# Release Cycle

## Stable Releases

Stable releases will only be pushed every 1-3 months, depending on the amount of features and quality. This stable release only comes after a beta cycle has been promoted to RC and the dev team all agree its stable enough to be promoted.

Patch releases on stable will be pushed if there if there is a real need, such as an important bugfix that was missed during beta but never any new functionality.

## Beta Releases

Beta releases are planned to be released every 1 - 4 weeks, depending on the amount of changes.

Once 2.0 is released, the beta of 2.1 will be started which starts with the same code base as 2.0 stable. Users can decide if they want to stay on the beta channel.

There is also a dev/nightly add-on which can be run to get the latest and greatest.

It is possible to run the stable, beta, dev server add-on side by side if desired as they don't share any data. Thus it is possible to temporarily run the beta add-on to try out new features and then stop it again.

## HA Integration

For the HA integration there will also be stable and beta releases if there is a need. For example, if there are any breaking changes (or new features) in the beta add-on, that will be a reason to also have a beta release of the HA integration. Folks running the MA server on the beta channel are advised to also run the HA integration in beta to prevent compatibility issues and vice versa.

