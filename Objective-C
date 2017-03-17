
#Objective-C（objc） 编码规范

命名规范 
=========================== 

`iOS`命名两大原则是:可读性高和防止命名冲突(通过加前缀来保证). `Objective-C` 的命名通常都比较长, 名称遵循驼峰式命名法. 一个好的命名标准很简单, 就是做到在开发者一看到名字时, 就能够懂得它的含义和使用方法. 另外, 每个模块都要加上自己的前缀, 前缀在编程接口中非常重要, 可以区分软件的功能范畴并防止不同文件或者类之间命名发生冲突, 比如相册模块`PhotoGallery`的代码都以`Cmos`作为前缀: `CmosAlbumViewController`, `CmosDataManager`.

#####Language

在开发项目中使用英文命名
推荐
```objc
UIColor *myColor = [UIColor whiteColor];
```

不推荐

```objc
UIColor *myColour = [UIColor whiteColor];
```
##### 组织代码

使用 `#pragma mark -` 在功能组别和协议/代理的地方加上相应的标示

```objc
#pragma mark - Lifecycle

- (instancetype)init {}
- (void)dealloc {}
- (void)viewDidLoad {}
- (void)viewWillAppear:(BOOL)animated {}
- (void)didReceiveMemoryWarning {}

#pragma mark - Custom Accessors

- (void)setCustomProperty:(id)value {}
- (id)customProperty {}

#pragma mark - IBActions

- (IBAction)submitData:(id)sender {}

#pragma mark - Public

- (void)publicMethod {}

#pragma mark - Private

- (void)privateMethod {}

#pragma mark - Protocol conformance
#pragma mark - UITextFieldDelegate
#pragma mark - UITableViewDataSource
#pragma mark - UITableViewDelegate

#pragma mark - NSCopying

- (id)copyWithZone:(NSZone *)zone {}

#pragma mark - NSObject

- (NSString *)description {}
```

##### 空格缩进

- 缩进使用2个空格
- 方法括号和其他括号总是在同一行的语句，但关闭一个新的行。

推荐

```objc
if (user.isHappy) {
  //Do something
} else {
  //Do something else
}
```
不推荐

```objc
if (user.isHappy)
{
    //Do something
}
else {
    //Do something else
}
```

推荐
```objc
// blocks are easily readable
[UIView animateWithDuration:1.0 animations:^{
  // something
} completion:^(BOOL finished) {
  // something
}];
```
不推荐
```objc
// colon-aligning makes the block indentation hard to read
[UIView animateWithDuration:1.0
                 animations:^{
                     // something
                 }
                 completion:^(BOOL finished) {
                     // something
                 }];
```

##### 方法的命名
在方法签名中，方法类型（+/-符号）后应该有空格。在方法段之间应该有一个空间（匹配苹果的风格）。总是包含关键字，并在描述参数的参数之前对单词进行描述性描述。
保留“and”这个词的用法。它不应该被用于在initWithWidth:height下面的例子。

推荐

```objc
- (void)setExampleText:(NSString *)text image:(UIImage *)image;
- (void)sendAction:(SEL)aSelector to:(id)anObject forAllCells:(BOOL)flag;
- (id)viewWithTag:(NSInteger)tag;
- (instancetype)initWithWidth:(CGFloat)width height:(CGFloat)height;
```

不推荐
```objc
-(void)setT:(NSString *)text i:(UIImage *)image;
- (void)sendAction:(SEL)aSelector :(id)anObject :(BOOL)flag;
- (id)taggedView:(NSInteger)tag;
- (instancetype)initWithWidth:(CGFloat)width andHeight:(CGFloat)height;
- (instancetype)initWith:(int)width and:(int)height;  // Never do this.

```

##### Property 属性命名

Property属性应显式列出，并将帮助新程序员阅读代码。属性的顺序应该是存储然后原子，这是自动生成的代码连接接口生成器UI元素一致时（Interface Builder）。

推荐
```objc
@property (weak, nonatomic) IBOutlet UIView *containerView;
@property (strong, nonatomic) NSString *tutorialName;
```
不推荐

```
@property (nonatomic, weak) IBOutlet UIView *containerView;
@property (nonatomic) NSString *tutorialName;
```

##### 点语法（Dot-Notation Syntax）

点语法纯粹是在访问器方法的一个方便的包装要求。当您使用点语法时，属性仍然被访问和设置方法。
点运算符应用于访问和变异的特性，因为它使代码更简洁。括号表示法在所有其他实例中是首选。

推荐

```objc
NSInteger arrayCount = [self.array count];
view.backgroundColor = [UIColor orangeColor];
[UIApplication sharedApplication].delegate;
```

不推荐

```objc
NSInteger arrayCount = self.array.count;
[view setBackgroundColor:[UIColor orangeColor]];
UIApplication.sharedApplication.delegate;
```

##### 常量的命名

对于常量的命名最好在前面加上字母k作为标记. 如:

> static const NSTimeInterval kAnimationDuration = 0.3;

定义作为NSDictionary或者Notification等的Key值字符串时加上const关键字, 以防止被修改. 如:

> NSString *const UIApplicationDidEnterBackgroundNotification 


 __Tips__

* 若常量作用域超出编译单元(实现文件), 需要在类外可见时, 使用extern关键字, 并加上该类名作为前缀. 如 extern NSString *const CmosThumbnailSize
* 全局常量(通知或者关键字等)尽量用const来定义. 因为如果使用宏定义, 一来宏可能被重定义. 二来引用不同的文件可能会导致宏的不同. P.S. 对于＃define也添加一下前缀k(强迫症, 哈哈...)

##### 枚举的命名

对于枚举类型, 经常会看到之前的C的定义方式:

```objc
typedef enum : {
    CameraModeFront,
    CameraModeLeft,
    CameraModeRight,
} CameraMode;
```

不知道是肿么了, 每次看到这种定义方式总是感觉怪怪的, 作为一个正宗的iOS开发者当然要以Objective-C的方式来定义啦, 哈哈... 那Objective-C是怎么定义的呢? 很简单, 到SDK里面看看Apple是怎么做滴:

```objc
typedef NS_ENUM(NSInteger, UIViewAnimationTransition) {
    UIViewAnimationTransitionNone,
    UIViewAnimationTransitionFlipFromLeft,
    UIViewAnimationTransitionFlipFromRight,
    UIViewAnimationTransitionCurlUp,
    UIViewAnimationTransitionCurlDown,
};
```

这边需要注意的是: 枚举类型命名要加相关类名前缀并且枚举值命名要加枚举类型前缀.

##### 变量和对象的命名

给一个对象命名时建议采用修饰+类型的方式. 如果只用修饰命名会引起歧义, 比如title (这个到底是个NSString还是UILabel?). 同样的, 如果只用类型来命名则会缺失作用信息, 比如label (好吧, 我知道你是个UILabel, 但是我不知道它是用来做什么的呀?). So, 正确的命名方式为:

titleLabel    //表示标题的label,  是UILabel类型
confirmButton //表示确认的button, 是UIButton类型

__Tips:__ 如果某个命名已经很明确了, 为了简洁可以省去类型名. 比如scores, 很明显是个array了, 就不必命名成scoreArray了

编码规范
===========================
**编码规范简单来说就是为了保证写出来的代码具备三个原则: [可复用][], [易维护][], [可扩展][]w. 这其实也是面向对象的基本原则. **

- 判断nil或者YES/NO

推荐

```objc
if (someObject) { ... } 
if (!someObject) { ... }

```
不推荐

```objc
if (someObject == YES) { ...} 
if (someObject != nil) { ...}
```
if (someObject == YES)容易误写成赋值语句, 自己给自己挖坑了...而且if (someObject)写法很简洁, 何乐而不为呢?


- 条件赋值

推荐

```objc
result = object ? : [self createObject];
```
不推荐

```objc
result = object ? object : [self createObject];
```
如果是存在就赋值本身, 那就可以这样简写, 多简洁啊, 哈哈...

- 初始化方法



推荐

```objc
NSArray *names = @[@"Brian", @"Matt", @"Chris", @"Alex", @"Steve"];
NSDictionary *productManagers = @{@"iPhone" : @"Kate", @"iPad" : @"Kamal"};
NSNumber *shouldUseLiterals = @YES;
NSNumber *buildingZIPCode = @10018;
```
第一个好处还是简洁, 第二个好处是可以防止初始化进去nil值造成crash

- 定义属性

推荐

```objc
@property (nonatomic, readwrite, copy) NSString *name;

```
建议定义属性的时候把所有的参数写全, 尤其是如果想定义成只读的(防止外面修改)那一定要加上readonly, 这也是代码安全性的一个习惯.
如果是内部使用的属性, 那么就定义成私有的属性(定义到.m的class extension里面)

对于拥有Mutable子类型的对象(e.g. NSString, NSArray, NSDictionary)一定要定义成copy属性. Why? 示例: NSArray的array = NSMutableArray的mArray; 如果mArray在某个地方改变了, 那array也会跟着改变. So, make sense?

尽量不要暴露mutable类型的对象在public interface, 建议在.h定义一个Inmutable类型的属性, 然后在.m的get函数里面返回一个内部定义的mutable变量. Why? For security as well!

- BOOL赋值

推荐
```objc
BOOL isAdult = age > 18;
```
不推荐
```objc
BOOL isAdult;
if (age > 18)
{
    isAdult = YES;
}
else
{
    isAdult = NO;
}
```

- 拒绝死值

推荐

```objc
if (car == Car.Nissan)
or
const int adultAge = 18; if (age > adultAge) { ... }

```
不推荐

```objc
if (carName == "Nissan")
or
if (age > 18) { ... }
```

死值每次修改的时候容易被遗忘, 地方多了找起来就悲剧了. 而且定义成枚举或者static可以让错误发生在编译阶段. 另外仅仅看到一个数字, 完全不知道这个数字代表的意义. 纳尼?

- 复杂的条件判断

推荐

```objc
if ([self canDeleteJob:job]) { ... }     
    
- (BOOL)canDeleteJob:(Job *)job
{
    BOOL invalidJobState = job.JobState == JobState.New
                          || job.JobState == JobState.Submitted
                          || job.JobState == JobState.Expired;
    BOOL invalidJob = job.JobTitle && job.JobTitle.length;
     
    return invalidJobState || invalidJob;
}
```

不推荐

```objc
if (job.JobState == JobState.New
    || job.JobState == JobState.Submitted
    || job.JobState == JobState.Expired
    || (job.JobTitle && job.JobTitle.length))
{
    //....
}

```

- 嵌套判断

推荐
```objc
if (!user.UserName) return NO;
if (!user.Password) return NO;
if (!user.Email) return NO;
 
return YES;
```
不推荐
```objc
BOOL isValid = NO;
if (user.UserName)
{
 
    if (user.Password)
    {
     
        if (user.Email) isValid = YES;
    }
     
}
return isValid;
```
一旦发现某个条件不符合, 立即返回, 条理更清晰

- 参数过多

推荐
```objc
- (void)registerUser(User *user)
{
 
     // to do...
      
}
```
不推荐
```objc
- (void)registerUserName:(NSString *)userName
                password:(NSString *)password 
                   email:(NSString *)email
{
     // to do...
}

```
当发现实现某一功能需要传递的参数太多时, 就预示着你应该聚合成一个model类了...这样代码更整洁, 也不容易因为参数太多导致出错。

- Case语句

当一个案例包含一个以上的行，括号应该增加。

```objc
switch (condition) {
  case 1:
    // ...
    break;
  case 2: {
    // ...
    // Multi-line example using braces
    break;
  }
  case 3:
    // ...
    break;
  default: 
    // ...
    break;
}
```

有时可以使用相同的代码为多个案例。

```objc
switch (condition) {
  case 1:
    // ** fall-through! **
  case 2:
    // code executed for values 1 and 2
    break;
  default: 
    // ...
    break;
}
```

当为开关使用枚举类型时，不需要默认值。例如:

```objc
CmosLeftMenuTopItemType menuType = CmosLeftMenuTopItemMain;

switch (menuType) {
  case CmosLeftMenuTopItemMain:
    // ...
    break;
  case CmosLeftMenuTopItemShows:
    // ...
    break;
  case CmosLeftMenuTopItemSchedule:
    // ...
    break;
}
```

- Private Properties
私有属性应该在类的实现文件中的类扩展（匿名类别）中声明。

```objc
@interface CmosDetailViewController ()

@property (strong, nonatomic) GADBannerView *googleAdView;
@property (strong, nonatomic) ADBannerView *iAdView;
@property (strong, nonatomic) UIWebView *adXWebView;

@end
```


- 回调方法

推荐

```objc
- (UITableViewCell *)tableView:(UITableView *)tableView cellForRowAtIndexPath:(NSIndexPath *)indexPath;
```
函数调用的可知性, 回调时被调用者要知道其调用者, 方便信息的传递, 所以建议在回调方法中第一个参数中加上调用者。


##### 单例（Singletons）
单件对象应该使用线程安全模式来创建它们的共享实例。
```objc
+ (instancetype)sharedInstance {
  static id sharedInstance = nil;

  static dispatch_once_t onceToken;
  dispatch_once(&onceToken, ^{
    sharedInstance = [[self alloc] init];
  });

  return sharedInstance;
}
```

Block的循环引用问题
===============================

Block确实是个好东西, 但是用起来一定要注意循环引用的问题, 否则一不小心你就会发现, Oh My God, 我的dealloc肿木不走了...

```objc
__weak typeof(self) weakSelf = self;
dispatch_block_t block =  ^{
    [weakSelf doSomething]; // weakSelf != nil
    // preemption, weakSelf turned nil
    [weakSelf doSomethingElse]; // weakSelf == nil
};
```

如此在上面定义一个weakSelf, 然后在block体里面使用该weakSelf就可以避免循环引用的问题. 那么问题来了...是不是这样就完全木有问题了? 很不幸, 答案是NO, 还是有问题。问题是block体里面的self是weak的, 所以就有可能在某一个时段self已经被释放了, 这时block体里面再使用self那就是nil, 然后...然后就悲剧了...那么肿么办呢?

```objc
__weak typeof(self) weakSelf = self;
myObj.myBlock =  ^{
    __strong typeof(self) strongSelf = weakSelf;
    if (strongSelf) {
      [strongSelf doSomething]; // strongSelf != nil
      // preemption, strongSelf still not nil
      [strongSelf doSomethingElse]; // strongSelf != nil
    }
    else {
        // Probably nothing...
        return;
         
    }
};
```
解决方法很简单, 就是在block体内define一个strong的self, 然后执行的时候判断下self是否还在, 如果在就继续执行下面的操作, 否则return或抛出异常.






