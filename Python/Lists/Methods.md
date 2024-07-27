- **append()**
    
    بنضيف بيها عناصر لليست
    
    ولو ضيفنا ليست لليست هتتضاف الليست دي كعنصر من ضمن العناصر
    
    ```Python
    myList = ["One", "Two", "Three", "Four", "Five"]
    myList2 = ["Six", "Seven", "Eight", "Nine", "Ten"]
    
    myList.append(myList2)  # Append List
    print(myList)
    
    #['One', 'Two', 'Three', 'Four', 'Five', ['Six', 'Seven', 'Eight', 'Nine', 'Ten']]
    ```
    
    هتكون ليست جوه الليست
    
    لو عايزين نوصل لعنصر بداخل الليست الي هيا داخل الليست
    
    هنا عندي 3 ليست جوه بعض
    
    في الاول محتاج اوصل لليست الاول هحط الاندكس بتاعه
    
    الليست التانيه في الاندكس 5 من الليست الاولي
    
    كده انا وصلت الاولي
    
    لو عايز اوصل لعناصر جواها هوصل بنفس الطريقه
    
    ```Python
    #['One', 'Two', 'Three', 'Four', 'Five',
    # ['Six', 'Seven', 'Eight', 'Nine', 'Ten', 
    #['Eleven', 'Twelve', 'Thirteen', 'Fourteen', 'Fifteen']]]
    
    myList = ["One", "Two", "Three", "Four", "Five"]
    myList2 = ["Six", "Seven", "Eight", "Nine", "Ten"]
    myList3 = ["Eleven", "Twelve", "Thirteen", "Fourteen", "Fifteen"]
    myList2.append(myList3)  # Append List
    myList.append(myList2)  # Append List
    print(myList[5][5][2]) # Thirteen
    ```
    
- **extend()**
    
    شبه الابيند لاكن هتضيف عناصر الليست مباشره مش هتضيف الليست كعنصر
    
    ```Python
    myList = ["One", "Two", "Three", "Four", "Five"]
    myList2 = ["Six", "Seven", "Eight", "Nine", "Ten"]
    myList3 = ["Eleven", "Twelve", "Thirteen", "Fourteen", "Fifteen"]
    # myList2.append(myList3)  # Append List
    # myList.append(myList2)  # Append List
    # print(myList[5][5][2])
    myList.extend(myList2)
    print(myList)
    
    #['One', 'Two', 'Three', 'Four', 'Five', 'Six', 'Seven', 'Eight', 'Nine', 'Ten']
    ```
    
    - When you use `extend`, you are appending the elements of one list to the end of another list.
    - It does not create a new list; it modifies the original list by adding the elements from the second list.
- **remove()**
    
    بتمشي علي الاراي وتمسح اول عنصر يقابلها ويحقق المطلوب
    
- **sort()**
    
    ```Python
    listNumbers = [4,5,2,1,0,9,8,7,6,3];
    listNumbers.sort()  # Ascending Order
    print(listNumbers)  # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
    listNumbers.sort(reverse=True)  # Descending Order
    print(listNumbers)  # [9, 8, 7, 6, 5, 4, 3, 2, 1, 0]
    ```
    
    ديفولت بترتب تصاعدي وبيكون جوه السورت ميثود ريفيرس بيساوي فولس
    
    يعني مترتبش تنازلي
    
    لو عايز ارتب تنازلي بباصي للفانكشن ريفيرس ترو
    
    **لازم الليست كلها تكون من نفس النوع**
    
- **reverse()**
    
    بتعكس الليست بغض النظر عن اتواع الداتا
    
    ```Python
    listNumbers2 = [4,5,2,1,0,9,8,7,6,3];
    listNumbers2.reverse()  # Reverse List
    print(listNumbers2)  # [3, 6, 7, 8, 9, 0, 1, 2, 5, 4]
    ```
    
      
    
      
    
      
    
- **clear()**
    
    بتفضي الليست
    
    مش بتمسحها
    
    بتمسح العناصر الي جواها
    
- **copy()**
    
    بتعمل شالو كوبي لليست جوه ليست تاني
    
    يعني عندي اتنين ليست عايز انسخ الاولي جوه التانيه
    
    واي تعديل يحصل فاي منهم بعد الكوبي مش هياثر علي واحده غيرها
    
    creating a new list that is a separate object in memory but contains the same elements as the original list.
    
    ```Java
    original_list = [1, 2, 3]
    copied_list = original_list.copy()
    
    copied_list.append(4)
    
    print(original_list)  # Output: [1, 2, 3]
    print(copied_list)    # Output: [1, 2, 3, 4]
    ```
    
- **count()**
    
    بتعد ظهور عنصر معين فالليست
    
    ```Python
    listt = [1 , 2 , 3 , 4 , 1 , 5 , 1 , 2]
    print(listt.count(1))
    ```
    
- **index()**
    
    بتجيب اندكس اول عنصر تلاقيه
    
    ```Python
    listt = [1 , 2 , 3 , 4 , 1 , 5 , 1 , 2]
    print(listt.index(2))
    ```
    
- **insert()**
    
    بتضيف عنصر قبل اندكس هديهوله
    
    الابيند كانت بتضيف فالاخر فقط
    
    بديله الاندكس وبعدين الاوبجكت الي هضيفه
    
    بيروح للاندكس ده وبعدين ييجي قبله ويضيف الاوبجكت
    
    ```Python
    listt = [1 , 2 , 3 , 4 , 1 , 5 , 1 , 2]
    listt.insert(2,5)
    listt.insert(-1,5)
    print(listt) # [1, 2, 5, 3, 4, 1, 5, 1, 5, 2]
    ```
    
- **pop()**
    
    بتمسح وترتيرن عنصر من اندكس معين
    
    الديفولت بتاعها بتمسح الاخير بس ممكن اباصيلها اندكس
    
    ```Python
    listt = [1 , 2 , 3 , 4 , 1 , 5 , 1 , 2]
    print(listt.pop(2))\#3
    print(listt.pop())\#2
    print(listt) #[1, 2, 4, 1, 5, 1]
    ```