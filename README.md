# scratchy-py

Scratch-inspired game engine for Python

Scratchy-py will bring Scratch concepts of autonomous, rich "Sprites" to 
Python. We intend it to be a great environment for learning programming 
and Python.

Scratchy-py is intended to run both in the browser and on the Desktop. The
browser is the highest priority, because we feel that it will be the 
educaitonal environment of the future.

You can see a very early prototype here:

https://trinket.io/python/9fbfc2523c

The protoype runs on [Processing.py](http://py.processing.org/) which runs on [Skulpt](http://www.skulpt.org/) which runs in the 
browser. [Trinket](https://trinket.io/python) is also a great environment for hosting these games.

So far, the biggest challenge that we have identified is that Scratch
uses cooperative multitasking in a very transparent way. Python threads
are not as seamless, and are not avaialable at all in Skulpt. Multitasking 
is  useful for code like this:

<pre>
def BounceAround():
	while 1:
		sprite.move(10)
		sleep(0.25)
		sprite.turn(random.random()*90)
		if sprite.touching_edge():
			sprite.turn(180)

</pre>

The team has been considering a variety of solutions to this, including
Python 3 co-routines, the addition of cooperative threads (built on 
Suspensions) and an event-based/message-based model.

