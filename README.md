OverflowScrollingFix
====================

OSFix tries to fix iOS5 native 'overflowScrolling:touch' glitches.

Released "AS IS" to the public domain

Notes
=====

The fix works 90% of the times, but it fails when swiping fast after the rubber band effect. Javascript totally looses control over the element while bouncing back in position so it's really hard to completely defeat this "bug".

Dirty fix
=========

If you don't want to include another library to your application the easiest way to get the fix is like so:

	var element = document.getElementById('element');
	element.addEventListener('touchstart', function () {
		var maxScroll = element.scrollHeight - element.offsetHeight;
		if (element.scrollTop <= 0) element.scrollTop = 1;
		else if (element.scrollTop >= maxScroll) element.scrollTop = maxScroll - 1;
	}, false);
