# OGLOED

This project is a stub.
I hope someone will adopt it (with or without Bountysource).

![2021-06-24_18-26](https://user-images.githubusercontent.com/51802145/123311217-7262b380-d516-11eb-9463-ada867dd7785.png)

OGLOED (OpenGL On an External Device) is a virtual video card architecture. It utilizes power of an external device GPU for additional needs: from rear view mirrors in racing simulators to game physics and crypto mining.
Unlike X11-compatible devices, proprietary "black boxes" can't simply run a remote X11 server for this — so dedicated solution is needed, such as OGLOED. Also, most of those devices can run OpenGL ES only, so it requires an additional conversion layer: on the device side if possible (it allows to use it's CPU power) or, at least, on the client side. Writing such conversion module for everything-on-Earth is not a realistic scenario, so in most cases only the mandatory module will be ported (it's very simple — it takes OpenGL ES input from LAN and forwards it to the local API).
In other words, one of three things must exist: the device itself must support OpenGL (not OpenGL ES), the conversion module must be ported for this device, or the PC must have enough surplus CPU power to feed the client-side conversion module (which can probably be based on a fully-software renderer such as LLVMpipe).
Backward data transmisson (such as screen taps and keyboard hits if any) is questionable, but implementing this will also allow OGLOED to work as a very safe remote desktop (only a dedicated application which uses the virtual video card can receive such control events).
