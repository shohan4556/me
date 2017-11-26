+++
date = "2017-11-01T00:00:00"
draft = false
tags = ["Coding", "C-Sharp", "Unity-3D"]
title = "Unity Tips - 01"
math = false
summary = """
Simple and easy to use Unity tips that will help to write code more smoothly.
"""

[header]
image = "headers/cover2.jpg"
caption = "Image credit: [**ME!**](#)"

+++
Hello there, I am going to write a short post about Unity Editor tips that will boost up your workflow. 

**Slider**

    [Range(1, 100)]
	public int weight;

This code will come up with a slider in inspector.

**OnValidate()**

Sometimes you may want to validate value that comes from inspector. Unity has a nice method `onValidate` you can validate value.

    public float speed;
	
	void onValidate()
	{
		if(speed<=0){
			Debug.LogError("Hey speed should be greater than 0");
		}
	}

**ToolTip**

Sometimes you may have deliver your project to dumb client, ToolTip can make your life easier. 

    [Tooltip("drop here the screaming audio from Assets ")]
    public AudioClip screamAudio;

**HideInInspector**	

Hide public variable form Inspector.

    [HideInInspector]
    public int p = 5;

**RequireComponent**

Use it for dependency script. Make your life easier. 

    [RequireComponent(typeof(Rigidbody))]
    public class PlayerScript : MonoBehaviour
	{
        Rigidbody rBody;
    
        void Start()
        {
            rBody = GetComponent<Rigidbody>();
        }
    }
        


----------


follow me on [facebook](https://www.facebook.com/shohan4556) 

follow me on [twitter](https://www.twitter.com/shohan4556) 

follow me on [github](https://www.github.com/shohan4556) 


