+++
date = "2017-11-01T00:00:00"
draft = false
tags = ["Unity-3D"]
title = "Laser2D Wiki"
math = false
summary = """
How to use Laser2D ...
"""

[header]
image = "Laser2D.png"
caption = "Image credit: [**ME!**](#)"

+++

**[Download](https://assetstore.unity.com/packages/vfx/particles/laser2d-81830)**

[web version of the doc](https://shohan4556.github.io/Laser2D/) - Recommended.

```
 Verssion : 0.02  
 Updated : December 2017 
 Developer : Shohanur Rahaman
 Contact : shohan4556@gmail.com 
 web : techshohan.me
```
----------


Features
-------------

 - Four directional Laser (Top, Down, Left, Right)
 - Modify Laser Color
 - Easy to Implement  
 - Mobile Friendly 
 - Great for Pixel Art Games

How To Use
-------------

1. [Getting Started](#Getting-Started)
2. [Changing Laser Color](#changing-laser-color)
3. [Understanding Inspector Variables](#understanding-inspector-variables)
4. [Using Four Directional Laser](#using-four-directional-laser)
5. Modify Code
	 1. [How to Add Enemy Damage](#how-to-add-enemy-damage)
	 2. [Modify Input](#modify-input)  
6. [Tips](#tips)
7. **More Features is Coming Soon**

----------
#### Getting Started
The easiest to way to see Use Laser2D create a **Parent Gameobject** (that could be player/ship sprite) then **drag the Prefab** and make it child of the parent object. Add the **Sprite Light** material to the enemy gameobject. Play the game and Click the **Right Mouse Button**.  

![Getting Started](https://i.imgur.com/3zBZ5Nx.gif)

#### Changing Laser Color
To Change a Laser Color go through the child object > find the **Laser Glow** gameobject and change the sprite color.

![Changing Laser Color](https://i.imgur.com/8iK3wlN.gif)

#### Understanding Inspector Variables
![Inspector](https://i.imgur.com/KHX1Rao.png) 

 - **Ray Begin Pos :** This is the position where the laser beam starts from.

- **Enemy Hit layer :** you Enemy should be in Enemy Layer, you can also add multiple layers.

- **Ray Size :** This is the invisible Ray size or Raycast Size.

- **Laser Size :** This is the visible Laser size. Adjust the size according to your need.

- **Laser Glow Size :** This is the Laser glow size adjust the size with **Laser Size**

- **Laser Damage :** This is the damage for the **Enemy**.

- **Ray Duration :** Laser firing duration in second.

- **Laser Hit Emitter :** Laser Hit emitter prefab.

- **Laser Melt Emitter :** Laser Melting Prefab. 

- **Laser Glow :** Laser glowing sprite.

- **Laser Dir :** Laser direction, use it for changing direction. Its not changeable in 
  
- **runtime** you need to define it before playing the game. Available laser direction **Top, Down, Left and Right**.

#### Using Four Directional Laser
The easiest way to use Four directional laser is using Prefab there are four prefabs 
**L2D-Top, L2D-Down, L2D-Left & L2D-Right** you can use any of them. 
There is another way is **Changing the Laser Direction.**

![Top-Down](https://i.imgur.com/WlAsU9c.png)

#### How to Add Enemy Damage
To give damage on Enemy gameobject create a tag name as **Enemy** and add it to the enemy object. Edit the code inside the **Update** method.
```
 /*-------------------- Enemy Damage -------------------- */
     if (hit.collider.tag == "Enemy") {
      hit.collider.gameObject.GetComponent<L2DEnemyHealth().giveDamage(laserDamage);
   }
 /*------------------------------------------------------ */
```

*Tips :* For better performance you can cache the EnemyHealth script inside Start method.

#### Modify Input
To modify input go through the ```LaserBeam``` script and find the ```FireLaser``` function you can find there the input code. Its easy to change the code. 
Here is an example, assumes that you have a script ```Myscript``` you can simply do it like this  from ```Myscript```
```
	public LaserBeam laserbeam; // drag the LaserBeam gameobject
	void Start()
	{
		if(laserbeam==null){
		   laserbeam = 	Gameobject.FindObjectOfType<LaserBeam>();
		}
	}
	
	void Update()
	{
	    if(	Input.GetButtonDown(keyCode.Space){
		 laserbeam.FireLaser();   
	    }
	}
```
*Note :* Don't forget to comment out the ```FireLaser``` method form the ```LaserBeam``` script.

#### Tips 
* Use **Order in Layer** for ordering Player sprite and Laser. I suggest you to use lower order to Player and higher order for Laser2D, it looks better than. 


-----------------


----------


follow me on [facebook](https://www.facebook.com/shohan4556) 

follow me on [twitter](https://www.twitter.com/shohan4556) 

follow me on [github](https://www.github.com/shohan4556) 


