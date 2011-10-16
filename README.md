OverflowScrollingFix
====================

OSFix tries to fix iOS5 native 'overflowScrolling:touch' glitches.

Released "AS IS" to the public domain

Notes
=====

The fix works 90% of the times, but it fails when swiping fast after the rubber band effect. Javascript totally looses control over the element while bouncing back in position so it's really hard to completely defeat this "bug".