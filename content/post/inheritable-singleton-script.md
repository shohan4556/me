+++
date = "2018-05-01T00:00:00"
draft = false
tags = ["Coding", "C-Sharp","Unity-3D"]
title = "Inheritable Singleton Pattern"
math = false
summary = """
সিঙ্গেলেটন একটা পরিচিত এবং জনপ্রিয় ডিজাইন প্যাটার্ন। অনেক সময় মাল্টিপল স্ক্রিপ্ট সিঙ্গেলেটন করতে হয়। একই জিনিস বার লেখা ঝামেলা সেজন্য inheritable singleton script ব্যাবহার করা যেতে পারে।
"""

[header]
image = "headers/my-unity-setup.png"
caption = "Image credit: [**me**](me)"

+++
সিঙ্গেলেটন একটা পরিচিত এবং জনপ্রিয় ডিজাইন প্যাটার্ন। অনেক সময় মাল্টিপল স্ক্রিপ্ট সিঙ্গেলেটন করতে হয়। একই জিনিস বার লেখা ঝামেলা সেজন্য inheritable singleton script ব্যাবহার করা যেতে পারে।
নিচে আমার নিজের লেখা একটি ইনহেরিটেবল স্ক্রিপ্ট। এই স্ক্রিপ্ট বার বার একই জিনিস লেখার ঝামেলা বাঁচাবে। যদি ছোট প্রোজেক্ট হয় তাহলে কাজে লাগবে না কারন ছোট খাটো প্রোজেক্টে অত বেশি সিঙ্গেলেটন দরকার হয় না সাধারণত।  

```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class SingletonBase<T> : MonoBehaviour where T : MonoBehaviour {
 
    private static object slock = new object(); safety 
    private static T sInstance; 

    public static T Instance
    {
        get {
            lock (slock) {
                if(sInstance == null) {
                    sInstance = GameObject.FindObjectOfType<T>(); 
                    if(sInstance == null) {
                        UnityEngine.Debug.LogError("Expected to find an instance of the " + typeof(T) + " component in the hierarchy but none found!\n"
                                     + "Attach the " + typeof(T) + " component to a GameObject in the hierarchy.");

                        Abort();
                    }
                    // got the instance
                    DontDestroyOnLoad(sInstance.transform.gameObject);
                }
                return sInstance;
            }
        }
    }

    private static void Abort() {
        #if UNITY_EDITOR
            UnityEditor.EditorApplication.isPlaying = false;
        #endif
    }

    private void Awake() {
        if(Instance != this) {
            Destroy(this.gameObject);
            return;
        }
    }

}
```

Little explanation : 
slock  একটা অবজেক্ট ক্রিয়েট করি । 
Lock ( ….) { } প্রথমে একটি থ্রেড এই ব্লকে ঢুকবে এবং লক করে ফেলবে অন্য কোন থ্রেড কে এখানে ঢুকতে দিবে না যতক্ষণ না এর কাজ শেষ হয়। খাটি বাংলায় এই হচ্ছে মূল কথা । কাজ শেষ হলে slock অবজেক্ট কে রিলিজ করে দিবে অর্থাৎ কাজ শেষ। 
প্রথমে ট্রাই করবো এরকম স্ক্রিপ্ট আরও আছে কিনা খোঁজার যদি না পাই তাহলে একটা এরর মেসেজ দিবো । 
আর যদি পাই তাহলে তো ভালো। 

কিভাবে ইনহেরিট করতে হবে ? 

```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
public class UIManager : SingletonBase<UIManager> {

    [SerializeField] private MainMenu mainMenu;
    [SerializeField] private Camera demoCamera;
 
    private void Update() {
        if (Input.GetKeyDown(KeyCode.Space)) {
            Debug.Log("fadeout UI manager");
            mainMenu.FadeOut();
        }
    }

    public void setDemoCameraActive(bool flag) {
        demoCamera.gameObject.SetActive(flag);
    }
}
```

রেফারেন্স ঃ 

1. https://www.codeproject.com/Articles/572263/A-Reusable-Base-Class-for-the-Singleton-Pattern-in
2. http://www.yoda.arachsys.com/csharp/singleton.html
3. http://wiki.unity3d.com/index.php/Singleton






----------


follow me on [facebook](https://www.facebook.com/shohan4556) 

follow me on [twitter](https://www.twitter.com/shohan4556)
 
follow me on [github](https://www.github.com/shohan4556) 