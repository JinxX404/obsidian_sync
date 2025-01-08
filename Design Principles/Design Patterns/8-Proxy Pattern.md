**Proxy** is a structural design pattern that lets you provide a substitute or placeholder for another object. A proxy controls access to the original object, allowing you to perform something either before or after the request gets through to the original object.

بيكون زي سكرتير او بوديجارد للreal object 
بيكون فالنص
وبتعدي عليه حاجات وهو يشوف اذا كان ينفع  تعدي وتوصل للreal object ولا لا
بيحدد التواصل control access 

البروكسي بيظهر للكلاينت ك انه هو ال real object (يعني هياخد من نفس الانترفيس الي واخد منها الreal)

![[Pasted image 20250108191718.png]]

هيكون عندي انترفيس هيimplements منها الservice والproxy 
البروكسي هيكون فيه اوبجكت من الservice 
وهيعمل اللوجيك فالبروكسي الي يخص الفلتر او الaccess او كاش او او 
ولو الكونديشن اتحقق هيستخدم الاوبجكت الي واخده من السيرفس في انه ينفذ الاوبريشن دي


###### How to Implement

1. If there’s no pre-existing service interface, create one to make proxy and service objects interchangeable. Extracting the interface from the service class isn’t always possible, because you’d need to change all of the service’s clients to use that interface. Plan B is to make the proxy a subclass of the service class, and this way it’ll inherit the interface of the service.
    
2. Create the proxy class. It should have a field for storing a reference to the service. Usually, proxies create and manage the whole life cycle of their services. On rare occasions, a service is passed to the proxy via a constructor by the client.
    
3. Implement the proxy methods according to their purposes. In most cases, after doing some work, the proxy should delegate the work to the service object.
    
4. Consider introducing a creation method that decides whether the client gets a proxy or a real service. This can be a simple static method in the proxy class or a full-blown factory method.
    
5. Consider implementing lazy initialization for the service object.
    

###### Pros and Cons

pros:
- You can control the service object without clients knowing about it.
- You can manage the lifecycle of the service object when clients don’t care about it.
- The proxy works even if the service object isn’t ready or is not available.
- _Open/Closed Principle_. You can introduce new proxies without changing the service or clients.
cons:
- The code may become more complicated since you need to introduce a lot of new classes.
- The response from the service might get delayed.

