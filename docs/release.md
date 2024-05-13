# Release Cycle

## Stable Releases

Stable releases will only be published every 1-3 months, depending upon the number of feature improvements. These stable releases will come after a beta cycle has been promoted to "Release Candidate" and the development team all agree its stable enough to be promoted.

Patch releases may be pushed if there is a compelling need (e.g. an urgent bugfix)

## Beta Releases

Beta releases are planned to be released every 1 - 4 weeks, depending on the number of changes.

Once 2.0 is released, the beta for version 2.1 will be available. It is possible to remain on the beta channel.

There is also a dev/nightly add-on which can be run to get the absolute latest version but this comes with risk of intermittent problems during the development cycle.

!!! warning
    This next section is for ADVANCED users. If you make a mistake you will have to remove all versions of the addon and start again. Be WARNED!

### Running Parallel Server Versions

It is possible to run the stable, beta or dev server add-ons side by side as they don't share any data. Thus you can temporarily run the beta add-on to try out new features and then revert to the stable version. You can do this in one of two ways:

1. If you setup the Integration with the `Use the official addon` checkbox ticked then disable the HA Integration which will stop the stable server. Now start the Beta/Dev server. Reverse this process to restore the stable server.

2. If you setup the HA Integration without selecting `Use the official addon` checkbox then you will have to manually start and stop the relevant servers

## HA Integration

For the HA integration there will also be stable and beta releases if there is a need. For example, if there are any breaking changes (or new features) in the beta add-on, that will be a reason to also have a beta release of the HA integration. People running the MA server on the beta channel are advised to also run the HA integration in beta to prevent compatibility issues and vice versa.
