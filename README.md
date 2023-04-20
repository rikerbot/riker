# Riker

## Getting started

### Development

A convenience script 'run.sh' can be used. This will setup a build process and then run the app in development mode.

```bash
./run.sh
```

### Production

### Design decisions

1) Represeting integration information for transport, storage

To make events accessible potentially within information sharing ecosystems Riker uses the [Signals](https://github.com/information-sharing-networks/signals) protocol (see simplest signal example).

For each integration (such as IRC) signals are composed and or reverse engineered as required.

For example with the IRC integration IRC messages include the required elements of a minimum signal by using a combination of information built into the IRC network (e.g. timestamp as the signal 'published' field) and fields deconstructed out of an event (via some payload) we are uplifting out of a silo or source location.

We delegate all aspects of the display and storage of the signal to the integration from this point with the exception of any information sharing network activity (e.g. transmission peer to peer for syndication etc). IRC stores the logs (if a sensible IRC client has been chosen).

A sample IRC message therefore could look like:

```
github.com/someuser edited issue at someorganisation/somerepo
```