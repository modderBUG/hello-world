# REST资源命名指南
## REST资源命名指南(REST Resource Naming Guide)  

在REST中，主要数据表示称为资源。 从长远来看，拥有一个强大且一致的REST资源命名策略–无疑将证明是最佳的设计决策之一。  

 >REST中信息的关键抽象是一种资源。 可以命名的任何信息都可以是资源：文档或图像，临时服务（例如“洛杉矶今天的天气”），其他资源的集合，非虚拟对象（例如人）等 上。 换句话说，任何可能成为作者超文本引用目标的概念都必须符合资源的定义。 资源是到一组实体的概念映射，而不是在任何特定时间点与该映射相对应的实体。  
      —罗伊·菲尔丁（Roy Fielding）的论文  
      
 **资源可以是单例或者集合。** 例如，"`customers`"是一个集合资源，"`customer`"是单例资源（在银行域中）。 我们可以使用URI"`/customers`"标识"`customers`"集合资源。 我们可以使用URI"`/customers/{customerId}`"来标识单个"`customer`"资源。  
 
 **资源也可以包含子集合资源。** 例如，可以使用URN"`/customers/{customerId}/accounts`" （在银行领域中）来标识特定"`customer`"的子集合资源"`accounts`"。 类似地，子集合资源"`accounts`"内的单例资源"`account`"可以如下标识："`/customers/{customerId}/accounts/{accountId}`"。  
 
 REST API使用统一资源标识符（URI）来寻址资源。 REST API设计人员应创建URI，以将REST API的资源模型传达给潜在的客户开发人员。 正确命名资源后，API直观易用。 如果做得不好，同样的API可能会难以使用和理解。  
 
 统一接口的约束部分通过URI和HTTP动词的组合并按照标准和约定来使用来部分解决。  
 
 以下是为新API创建资源URI时应遵循的一些技巧。  
 
## REST资源命名最佳实践  
    
### 使用名词来表示资源
 
RESTful URI应该引用作为事物（名词）的资源，而不是引用动作（动词），因为名词具有动词所没有的属性–类似于资源具有属性。 资源的一些示例是：  

+ 系统用户  
+ 用户帐号  
+ 网络设备等  

其资源URI可以设计如下：
````
http://api.example.com/device-management/managed-devices 
http://api.example.com/device-management/managed-devices/{device-id} 
http://api.example.com/user-management/users/
http://api.example.com/user-management/users/{id}
````

为了更清楚，让我们将 **资源原型**分为四类（文档，集合，存储和控制器），然后 **您始终应该将资源放在一种原型中，然后始终使用其命名约定。** *为了统一起见，请抵制设计资源的诱惑，这些资源是多个原型的混合体。*  

1. **文档(document)**  

文档资源是单个概念，类似于对象实例或数据库记录。 在REST中，您可以将其视为资源集合中的单个资源。 文档的状态表示形式通常包括带有值的字段以及指向其他相关资源的链接。  

使用“单一”名称表示文档资源原型。  
````
http://api.example.com/device-management/managed-devices/{device-id}
http://api.example.com/user-management/users/{id}
http://api.example.com/user-management/users/admin
````

2. **集合(collection)**  

集合资源是服务器管理的资源目录。 客户可以建议将新资源添加到集合中。 但是，由集合决定是否创建新资源。 收集资源选择它要包含的内容，并确定每个包含的资源的URI。  

使用“多个”名称表示收集资源原型。  
```
http://api.example.com/device-management/managed-devices
http://api.example.com/user-management/users
http://api.example.com/user-management/users/{id}/accounts
```
3. **储存(store)**  

储存是客户端管理的资源存储库。 存储资源使API客户端可以放入资源，将其撤回并决定何时删除它们。 商店永远不会生成新的URI。 取而代之的是，每个存储的资源都有一个URI，该URI是客户端最初将其放入商店时选择的。  

使用“多个”名称表示商店资源原型。  
```
http://api.example.com/cart-management/users/{id}/carts
http://api.example.com/song-management/users/{id}/playlists
```
4. **控制器(controller)**  

控制器资源为过程概念建模。 控制器资源就像可执行函数一样，带有参数和返回值。 输入和输出。  

使用“动词”表示控制器原型。  
```
http://api.example.com/cart-management/users/{id}/cart/checkout
http://api.example.com/song-management/users/{id}/playlist/play
```
### 一致性是关键

使用一致的资源命名约定和URI格式，以最大程度地减少歧义并最大程度地提高可读性和可维护性。 您可以实现以下设计提示以实现一致性：  

1. #### 使用正斜杠（/）表示层次关系  

   URI的路径部分使用正斜杠（/）字符表示资源之间的层次关系。 例如
   ```
   http://api.example.com/device-management
   http://api.example.com/device-management/managed-devices
   http://api.example.com/device-management/managed-devices/{id}
   http://api.example.com/device-management/managed-devices/{id}/scripts
   http://api.example.com/device-management/managed-devices/{id}/scripts/{id}
   ```
2. #### 请勿在URI中使用尾部正斜杠（/）
   作为URI路径中的最后一个字符，斜杠（/）不添加任何语义值，并可能引起混淆。 最好将它们完全丢弃  
   ```
   http://api.example.com/device-management/managed-devices/
   http://api.example.com/device-management/managed-devices 	/*This is much better version*/
   ```
 3. #### 使用连字符（-）来提高URI的可读性  
   为了使您的URI易于人们扫描和解释，请使用连字符（-）来提高长路径段中名称的可读性。  
 
   ```
   http://api.example.com/inventory-management/managed-entities/{id}/install-script-location  //More readable
   http://api.example.com/inventory-management/managedEntities/{id}/installScriptLocation  //Less readable
   ```
 4. #### 请勿使用下划线（_）  
     可以使用下划线代替连字符作为分隔符–但是，根据应用程序的字体，下划线（_）字符可能会在某些浏览器或屏幕中被部分遮挡或完全隐藏。  
     
     为避免这种混淆，请使用连字符（-）代替下划线（_）。  
    ```
    http://api.example.com/inventory-management/managed-entities/{id}/install-script-location  //More readable
    http://api.example.com/inventory_management/managed_entities/{id}/install_script_location  //More error prone
    ```
 
 5. #### 在URI中使用小写字母
    方便时，在URI路径中应始终首选小写字母。  
    
    RFC 3986将URI定义为区分大小写，但方案(scheme)和主机组件(host components)除外。 例如  
    ```
    http://api.example.org/my-folder/my-doc  //1
    HTTP://API.EXAMPLE.ORG/my-folder/my-doc  //2
    http://api.example.org/My-Folder/my-doc  //3
    ```  
    在上面的示例中，1和2相同，但3不是，因为它使用大写字母 **My-Folder**。
 6. #### 不要使用文件扩展名  
    文件扩展名看起来很糟糕，并且没有任何优势。 删除它们也会减少URI的长度。 没有理由保留它们。  
    除上述原因外，如果您想使用文件扩展名突出显示API的媒体类型，则应依靠通过Content-Type标头传达的媒体类型来确定如何处理正文内容。  
    ```
    http://api.example.com/device-management/managed-devices.xml  /*Do not use it*/
    http://api.example.com/device-management/managed-devices 	/*This is correct URI*/
    ```
### 切勿在URI中使用CRUD函数名称   
   URI不应用于指示执行CRUD功能。 URI应该用于唯一标识资源，而不是对资源进行任何操作。 应该使用HTTP请求方法来指示执行了哪个CRUD功能。   
   ```
   HTTP GET http://api.example.com/device-management/managed-devices  //Get all devices
   HTTP POST http://api.example.com/device-management/managed-devices  //Create new Device
   
   HTTP GET http://api.example.com/device-management/managed-devices/{id}  //Get device for given Id
   HTTP PUT http://api.example.com/device-management/managed-devices/{id}  //Update device for given Id
   HTTP DELETE http://api.example.com/device-management/managed-devices/{id}  //Delete device for given Id
   ```
### 使用查询组件过滤URI集合  
   很多时候，您会遇到一些需求，在这些需求中，您将需要根据某些资源属性对资源进行排序，过滤或限制的集合。 为此，请勿创建新的API，而应在资源收集API中启用排序，过滤和分页功能，并将输入参数作为查询参数传递。 例如
```
http://api.example.com/device-management/managed-devices
http://api.example.com/device-management/managed-devices?region=USA
http://api.example.com/device-management/managed-devices?region=USA&brand=XYZ
http://api.example.com/device-management/managed-devices?region=USA&brand=XYZ&sort=installation-date
```
   
   
   
   
   
   