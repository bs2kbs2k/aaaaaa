# @extends

## #eventsmoved

When we transform the blocks into JavaScript, we always place all the event registrations (block broken, arrow shot, ...) before launching the `||loops:on start||` code.

If a block from `||loops:on start||` pauses, other registered events will have the opportunity to run as well.