# Displaying Log Messages
#design 

**Q:** How to display messages to the user without popping up an overlay?

I want to write log messages in a heads up way on the screen.

- Displayed for a brief time, then they go away.
- Should be able to display multiple, either at the same time or sequentially.
	- Maybe two or three at once?
- Should consider using drawing effects instead of log messages where appropriate.
	- I.e., damage should be shown next to the thing damaged, not in the log.
- It seems like an animation.
- I think I need a queue, either real or virtual.
	- Each log message is an entity with a final time tick and a message.
		- Animator needs access to the time tick, manages the messages.
		- Only three messages; newer force out older
		- Display stacked, newest lowest.
	- Renderer renders.

_Created on 2021-12-22._