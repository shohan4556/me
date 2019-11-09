+++
date = "2019-11-09T00:00:00"
draft = false
tags = ["Coding", "C-Sharp"]
title = "How to save ScriptableObject data"
math = false
summary = """
I will show you a a simple trick, you can convert your SO object as playerpref. 
"""

[header]
image = "headers/alpha-racer-UI.png"
caption = "Image credit: **Me!**"

+++

What is the purpose of scriptable object ? 

> Saving and storing data during an Editor session (not in game mode)

> Saving data as an Asset in your Project to use at run time (like class)

so the basic idea is 

    1. parse the scritable object as JSON data
    2. save them in PlayerPrefs as string 

Here is a script I used one of my project : 
   
```
using System;
using System.Collections;
using System.Collections.Generic;
using UnityEditor;
using UnityEngine;
using Random = UnityEngine.Random;

/// <summary>
/// Author : Shohanur Rahaman 
/// </summary>
[CreateAssetMenu(fileName = "wave info", menuName = "Zombie/Wave", order = 1)]
public class WaveInfo_SO : ScriptableObject {
    
    [TextArea]
    public string name;
    public string saveKey;
   
    [Header("Zombie Properties")]
    public int totalWave = 1;
    public int zombiePerWave = 1;
    public int waveInterval = 2;
    public GameObject[] zombiePrefab;
    
    private void OnValidate(){
        if (saveKey.Equals("")) {
            saveKey = name;
        }
    }

    public GameObject GetZombie(){
        GameObject z = zombiePrefab[Random.Range(0, zombiePrefab.Length)];
        return z;
    }

    public void UpdateWaves(){
        totalWave -= 1;
    }

    public int GetWaveCount(){
        return totalWave;
    }

    private void OnEnable(){

            // get data 
            JsonUtility.FromJsonOverwrite(PlayerPrefs.GetString(saveKey), this);
            EditorJsonUtility.FromJsonOverwrite(PlayerPrefs.GetString(saveKey), this);
            Debug.Log("overwrite data");
        
    }

    private void OnDisable(){
        // save data 
            if (saveKey.Equals("")) 
                saveKey = this.name;
            
            string jsonData = JsonUtility.ToJson(this, true);
            //Debug.Log(jsonData);
            PlayerPrefs.SetString(saveKey, jsonData);
            PlayerPrefs.Save();
        
    }
}     
```
----------


follow me on [facebook](https://www.facebook.com/shohan4556) 

follow me on [twitter](https://www.twitter.com/shohan4556)
 
follow me on [github](https://www.github.com/shohan4556) 