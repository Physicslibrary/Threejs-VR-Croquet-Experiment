# Threejs-VR-Croquet-Experiment (under construction)
Explore Croquet real-time shared VR experiences with Threejs<br>

<img src="threejs-croquet-dec-10-2021.gif" width="240">

# Hardware

Oculus Quest (tested Quest One, update 35.0, Oculus browser 18.0)<br>

A Raspberry Pi 4 is used as a local web server and connected to internet (for reflectors to work).<br>

# Installation

Get a free developer's API key from:

https://www.croquet.io/

<pre>

Croquet.Session.join({

	appId: "com.example.myapp",   // namespace for session names
	apiKey: "your_api_key",       // paste from croquet.io/keys
	name: "unnamed",
	password: "secret",
	model: MyModel,
	view: MyView,
	step: "manual",
	}).then(session => {
	window.session = session;

	document.body.appendChild(VRButton.createButton(renderer));
	renderer.xr.enabled = true;
	renderer.setAnimationLoop(function() {
	controls.update();
	renderer.render(scene, camera);
	if (window.session && window.session.view) {
	window.session.step();
	}
  });

</pre>

# Credits

https://www.croquet.io/

https://threejs.org/

# References

https://www.croquet.io/docs/croquet/
