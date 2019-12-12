## 这个工程使用的Spring Boot 2 以上的版本

## 算法
- 算法：
    - book: 编程之法：面试和算法心得  https://wizardforcel.gitbooks.io/the-art-of-programming-by-july/content/a.14.html
    - leetcode分类总结 https://lefttree.gitbooks.io/leetcode-categories/sum/kSum.html
    - 其他：https://www.douban.com/note/330562764/   https://wdxtub.com/interview/14520604912864.html
- com.hry.algorithm
    - leetcode leetcode算法题
        - L001TwoSum: https://leetcode.com/problems/two-sum/submissions/
            - twoSum_1：穷举法
                - 执行时间25ms , 22.49%
            - twoSum_2： 用hashmap保存访问过的value, 对每个num[i],检查hashmap中是否有target - nums[i],扫完一遍就能够得到结果
                - 执行时间3ms, 50%
        - AddTwoNumbers：https://leetcode.com/problems/add-two-numbers/
            - 有疑问
        - LongestPalindromicSubstring： 最长回文
            - https://leetcode.com/problems/longest-palindromic-substring/submissions/
            - 算法1: 从第0个字符开始，每个字符向左右两边扩展，判断是否是回文。考虑回文是偶数和奇数情况
            - 执行时间：15ms, 57.06%
        - LongestSubstringWithoutRepeatingCharacters： https://leetcode.com/problems/longest-substring-without-repeating-characters/submissions/
            - lengthOfLongestSubstring1()方法：O(n2)，2次for循环+使用set保持已经遍历的字符
                - 45ms 18.90%
            - lengthOfLongestSubstring2()方法：O(n)，1此for循环 + HashMap保留每个字符最近的索引（如果当前char的索引 < j，则忽略，否则替换）
                - 7m 82.28%
        - MedianOfTwoSortedArrays: https://leetcode.com/problems/median-of-two-sorted-arrays/submissions/
            - 将两个数组合并到一个数据，取中间数的值（单数：n/2, 双数：n/2-1,n/2）: a. 比较两个数组，合并到数组，直至一个数组结束; b.第一个数组跌倒到末尾; c. 第二个数组跌倒到末尾;
            - 执行时间： 2ms 99.97
        - L007ReverseInteger：翻转整形
            - 考虑整形翻转后溢出的问题，新的值使用long; 
            - 执行时间： 1ms, 100%
        - L008StringToInteger:
            - 重点：a. 字符串转化整形，即使使用long，还不够，需要特殊处理； b. 将char的处理分为 首字符处理+continue 和 0-9 处理  
            - 执行时间: 1ms 100%
        - L009PalindromeNumber: 测试整数是否为回文
            - 重点：a. 特殊值： <0, 0<x<9;  b. 回文的判断：偶数和奇数
            - 执行时间 7m 67.93%
        - L012IntegeToRoman: 整形转化为罗马数字
            - 重点：列出每位的可能值
            - 执行时间 5ms 100%
        - L015Sum3：从数组中找出所有的3个数相加为0的组合
            - threeSum_1：穷举法
                - 执行时间，太久，无法通过
            - threeSum_1：a. sort + 双指针;  b. one + 2sum()
                - 执行时间：43ms 38.59%
         - L017LetterCombinationsofaPhoneNumber:
            - letterCombinations: 递归 a. 使用 sb 保存字符； b. helper(a) = heler(idx) + heler(a-idx);  c. 每个idx处理循环字符数组: 添加到sb,执行 heler(a-idx)，从新增sb d. 当 idx 超过数字长度，则结束，将结果添加到列表中
                - 执行时间 0ms 100%
            - letterCombinations2 : a. LinkedList; b.将每个数字对应字符一次推入列表；在下一个数字时，循环已有所有的字符，并添加新数字所有对应的字符，并加入队列尾巴；循环直至，数字循环一遍
                - 执行时间 0ms 100%
         - L020ValidParentheses：
            - 重点：a. LinkedList 做为 堆栈使用，新进后出： addFirst, poll; b. 左括号加入列表，如果是右括号，则将列表数据弹出，并获取对应的右括号，并比较两者是否相同
            - 执行时间 1ms 98.83% 
        - L021MergeTwoSortedLists
            - 重点：a. 头节点手动创建; b. 循环向后查找，直至一个队列为空； c. 非空队列
            - 执行 0ms , 100% 
        - L022GenerateParentheses
            - 重点：a. 递归：结束时间； b. 递归组合字符串使用sb，测试一个分支后，需要进行回退，如删除新加的值；c. 左括号数量 > 右括号数量，才可以添加右括号；反之左括号没有限制
            - 执行 1ms 94.76%
        - L023MergeKSortedLists
            - 解法一：mergeKListsByPriorityQueue() a. 使用PriorityQueue
                - 执行时间：6 ms 51.86%
            - 解法二：mergeKLists(): sort + merge  -> 归并排序
                - 执行时间：2ms 99.43
        -  L024SwapNodesInPairs 
            - 解法：
                - 重点：执行循环是，使用临时变量避免出现循环
                - 执行时间  0ms 100%
        - L027RemoveElement
            - 解法： 双指针
                - 执行时间 0ms 100%
    - recursive 递归算法
        - NQueen/NQueenII： 八皇后问题
    - sort：八大排序算法： https://cloud.tencent.com/developer/article/1114692
        - letcode: https://leetcode.com/problems/sort-an-array/submissions/
        - 插入排序:InsertSort （队列分为两部分，左边是已经排序好的，从右边未排序队列中获取值，并按照顺序插入左边队列中）
            - 执行时间 593 ms
        - 希尔排序: ShellSort （记录按下标的一定增量分组，对每组使用直接插入排序算法排序）
        - 选择排序: SelectionSort（从未排序的队列中选取一个最小/大值）
        - 冒泡排序: BubbleSort（重复比较相邻的两个值）
            - 执行时间超时
        - 归并排序：MergeSort （是利用归并的思想实现的排序方法，该算法采用经典的分治（divide-and-conquer）策略（分治法将问题分(divide)成一些小的问题然后递归求解，而治(conquer)的阶段则将分的阶段得到的各答案"修补"在一起，即分而治之)。）
            - 执行时间 6ms
        - 快速排序：QuickSort（）
            - 执行时间 5ms
        - 堆排序: HeapSort （1. 从最后一个非叶子节点开始，循环向上完成大堆的排序； 2. 将0个元素和最后交换，再对0-(length-1)执行排序；3. 子树大堆排序：首元素排序，从左右节点选取大的比较，和首元素比较，如果小于首元素，则结束，否则交换， 循环向下层处理）
            - 执行时间 578 ms -> 9s
        - 基数排序：RadixSort
            - 目前此算法只支持正整数
          

## apache: apache中通用的组件用法
- com.hry.java.apache
	- beanutils
		- BeanUtilTest：BeanUtil的常用操作方法
		- ConstructorUtilsTest：预留
		- ConverterTest：注册转换类
		- PropertyUtilsTest：类似BeanUtil
    - io: io操作demo
        - FilenameUtilsDemo: 对文件名、文件路径、文件扩展名操作的封装
        - FileUtils：对文件操作
            - 文件：复制、移动
            - 文件：把字符串列表、字符串、字节数组写入文件；读取文件到字符串列表、字符串、字节数组
            - 文件夹：创建、复制、删除、清空
            - 其他：获取临时文件、文件夹、文件大小、文件的修改时间修改和比较
    - lang3
		- ArrayUtilsTest：对数组进行操作类
	    - DateUtilsTest: 日期操作工具类
		- RandomStringUtilsTest：生成随机字符串
		- RandomUtilsTest：生成随机数字
		- SerializationUtilsTest: 序列化操作
		- StringEscapeUtilsTest: 对各种语言中的非法字符串进行加密解密
		- StringUtilsTest：对字符串操作
		- SystemUtilsTest：获取环境变量，包括预先定义的Java的环境变量
		- ValidateTest: 对输入的数据进行合法性检查

## fastjson
- com.hry.java.fastjson
    - serializer
	    - VO：序列化和各种注解使用; 序列化; 定义key名称，定义字段顺序，格式化时间
	- simple
		- SimpleMain：最简单的应用
## guava : guava的基本用法
    
## javaassist: javassist 基本用法

## javabasic: jdk的基本用法 
- com.hry.java
    - cls: class的反射用法
    - consistencyhash: 一致性哈希散列函数的实现
    - concurrent: 多线程用法
        - Semaphore信号量用法
    - lambda: lambda的用法 
        - CollectorsDemo
            - 过滤：按照给定的要求对集合进行筛选满足条件的元素，java8提供的筛选操作包括：filter、distinct、limit、skip
            - 映射：仅输出需要的字段数据。主要包含两类映射操作：map和flatMap。
                - map:扩展方法有mapToDouble、mapToInt、mapToLong
                - flatMap:与map的区别在于 flatMap是将一个流中的每个值都转成一个个流，然后再将这些流扁平化成为一个流
                    - 扩展方法：flatMapToDouble、flatMapToInt、flatMapToLong
            - 查找：match。allMatch、anyMatch、noneMatch、findFirst、findAny
            - 归约: reduce。对经过参数化操作后的集合进行进一步的运算
            - collect 归约操作
                - 简单的收集操作，是对处理结果的封装：Collectors.toList、Collectors.toSet、Collectors.toMap
                -  计算列表数量：Collectors.counting() 或stream().count()
                -  最大年龄：(Collectors.maxBy
                -  最小年龄：Collectors.minBy
                -  列表值相加：Collectors.summingInt
                -  一次性得到元素个数、总和、均值、最大值、最小值: IntSummaryStatistics
                -  字符串拼接：Collectors.joining()
            - collect 分组 操作
                - 对列表进行分组，并可对分组进行操作：Collectors.groupingBy
            - collect 分区 操作
                - 分区可以看做是分组的一种特殊情况，在分区中key只有两种情况：true或false：Collectors.partitioningBy
        - StreamsEffectivenessDemo：测试串行和并行stream的执行时间，两者相差一倍
    - path：java中各类路径用法
        - JavaBasePathMain: Java获取本地路径的多种方式
    - regular: 正则表达式的用法
        - NumberRegular： 从字符串中过滤出数字，或相反的操作
        - PatternDemo:  Pattern实例是不可变的，可线程安全; Matcher不支持并发请求
    - unsafe
        - Unsafe类的用法演示
    - utils: 工作类
        - DateUtils：时间格式化操作类，时间操作类
    - xml: JAXB：实现xml和java对象互转
        - JAXBManager：基本用法，演示@XmlRootElement，@XmlAccessorType，@XmlElement用法
        - JAXBManager：演示 @XmlAttribute， @XmlJavaTypeAdapter，XmlAdapter用法
## httpclient: httpclient的用法
- com.hry.java.httpclient.
    - example
        - CloseableHttpClientGetTest: 模拟get请求
        - CloseableHttpClientGetWithParameterTest: 带参数的get请求
        - CloseableHttpClientPostTest: 模拟post请求 -- 未实现
        - 异常HttpAsyncClients、https、Post、Get的方法的应用
    - httpclient45
    	- example：官方例子
    	- 其他后续再做：requestConfig、连接池、cookie、模拟登录、代理、Chunk、Credentials、POST/GET、form, request、SSL、文件上传
## jsoup: jsoup用法 
- 详细的用法见博客[Jsoup使用总结](https://blog.csdn.net/hry2015/article/details/72904416)
## lua：lua的脚本用法

## mock: mock的基本用法
- com.hry.mock
    - third：调用第三方的mock测试

## netty: netty的用法总结
- com.hry.java.netty
    - 通过客户端和服务端模拟netty通信
## tess4j:  文字、图片的文字识别
- com.hry.java.tess4j:
    - TesseractChinesePdfTest: OCR解析PDF中文文档
	- TesseractChineseTest: OCR解析中文图片截图
	- TesseractPdfTest：OCR解析pdf英文文档
	- TesseractTest：OCR解析图片
# thumbnailator:生成图像缩略图
- thumbnailator是一个用来生成图像缩略图的Java类库
- com.hry.java.thumbnailator.simple： 演示组件对图片如下的操作
    - 指定大小进行缩放
    - 按照指定比例进行缩放
    - 不按照比例，强制指定大小进行缩放
    - 对图片进行旋转
    - 为图片增加水印
    - 对图片进行裁剪
    - 转化图片格式
    - 对文件夹所有图片进行操作
## zookeeper: zookeeper的用法
- com.hry.java.zookeeper：暂时没试试
    - 1


