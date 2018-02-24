+++
date = "2018-02-24T00:00:00"
draft = false
tags = ["Artificial Intelligence", "C-Sharp", "Unity-3D"]
title = "Genetic Algorithm With Machine Learning"
math = false
summary = """
এখানে DNA factor গুলো হচ্ছে r,g,b color and scale. প্রথমে randomly rgb value এবং scale এর পপুলেশন জেনারেট করি।  পপুলেশন সাইয হচ্ছে ১০ এবং ...
"""

[header]
image = "headers/genetic-algo.png"
caption = "Image credit: [*Me!**](#)"

+++
![Natural Selection](https://i.imgur.com/LJs99AY.png)

আমি একটা মেশিন লার্নিং সিমুলেশন করি যেখানে Natural Selection বিষয়টা ছোট আকারে সিমুলেট করি।

এখানে DNA factor গুলো হচ্ছে r,g,b color and scale. প্রথমে randomly rgb value এবং scale এর পপুলেশন জেনারেট করি।  পপুলেশন সাইয হচ্ছে ১০ এবং জেনারেশন টাইম হচ্ছে ১০ সেকেন্ড। ১০ সেকেন্ড পর একটা জেনারেশন এর সব পপুলেশন ডেড হয়ে যাবে এবং এই পপুলেশনএর DNA data গুলো পরবর্তী পপুলেশনে  ইনহেরিট করবে। এখানে সেই ডাটাগুলোর priority level বেশি থাকবে যারা বেশি সময় ধরে সারভাইভ করতে পেরেছে (অর্থাৎ সবার শেষে সেটা ডেড)।  এই ডাটা গুলোরও পরবর্তীতে প্রজন্মে ইনহেরিট করার সম্ভাবনা ৫০% এবং মিউটেশন হচ্ছে  ০.১০% (বেশি মিউটেশন হলে আসল কালার টা হারিয়ে যেতে পারে তাই কম দিয়েছি)।

এই [ভিডিও](https://streamable.com/og91d) ক্লিপে দেখুন আমি রেড কালার টা সব শেষে remove করি নবম জেনারেশনেই আমি লাল এর আর একটা শেড পাই মিউটেশন এর কারনে। যেহেতু পপুলেশন সাইজ ছোট তাই খুব অল্প সময়েই রেজাল্ট দেখা যাচ্ছে।

এবার এই [ক্লিপে](https://streamable.com/0frnu) দেখুন এখানে পুরো সিমুলেশনটা অটোমেটেড, কোন সেলেক্টিভ পিকিং হয় নাই। পুরোটাই randomly selection। এখানে পপুলেশন সাইজ ২৫। ৪০তম জেনারেশনে গিয়ে নীল রঙের একটা শেড পাওয়া যাচ্ছে।

[source code](https://github.com/shohan4556/Genetic-Algorithm-With-Machine-Learning) 

----------


follow me on [facebook](https://www.facebook.com/shohan4556) 

follow me on [twitter](https://www.twitter.com/shohan4556) 

follow me on [github](https://www.github.com/shohan4556) 


