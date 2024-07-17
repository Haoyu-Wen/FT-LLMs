[toc]

## 说明:

test data 1/2 是 sample的test data

ICL data 1/2 是编造的测试模型ICL能力的data

xx Model Response 是某个模型的response（按照test data 1-2， ICL data 1-2顺序回答的，有删减重复部分）

xx Loss 是微调过程的Loss曲线、log

## Test Data 1

```
context:
Council member: I recommend that the abandoned shoe factory be used as a municipal emergency shelter. Some council members assert that the courthouse would be a better shelter site, but they have provided no evidence of this. Thus, the shoe factory would be a better shelter site.

question:
A questionable technique used in the council member's argument is that of

choices:
0:accepting a claim simply because advocates of an opposing claim have not adequately defended their view
1:attacking the proponents of the courthouse rather than addressing their argument
2:attacking an argument that is not held by any actual council member
3:asserting that a lack of evidence against a view is proof that the view is correct



 ### Output:

```

## Test Data 2

```
context:
An advertisement states: Like Danaxil, all headache pills can stop your headache. But when you are in pain, you want relief right away. Danaxil is for you -- no headache pill stops pain more quickly. Evelyn and Jane are each suffering from a headache. Suppose Evelyn takes Danaxil and Jane takes its leading competitor.

question:
Which one of the following can be properly concluded from the claims in the advertisement?

choices:
0:Evelyn's headache pain will be relieved more quickly than Jane's.
1:Evelyn's headache pain will be relieved, but Jane's will not.
2:Jane will be taking Danaxil for relief from headache pain.
3:Evelyn's headache will be relieved at least as quickly as Jane's.



 ### Output:
```

## ICL data 1

```
  Circulation revenue has increased by 5% in Finland. // Positive

  Panostaja did not disclose the purchase price. // Neatral

  Paying off the national debt will be extremely painful. // Negative

  The company anticipated its operating profit to improve. //
```

## ICL data 2

```
  Circulation revenue has increased by 5% in Finland. // Finance

  They defeated ... in the NFC Championship Game. // Sports

  Apple ... development of in-house chips. // Tech

  The company anticipated its operating profit to improve. //
```

## Base Response

```
Base_model:
&&&&&&&&&&&&&&&&&&
### According to given context, question and choices, choose   the correct answer: 
context:
Council member: I recommend that the abandoned shoe factory be used as a municipal emergency shelter. Some council members assert that the courthouse would be a better shelter site, but they have provided no evidence of this. Thus, the shoe factory would be a better shelter site.

question:
A questionable technique used in the council member's argument is that of

choices:
0:accepting a claim simply because advocates of an opposing claim have not adequately defended their view
1:attacking the proponents of the courthouse rather than addressing their argument
2:attacking an argument that is not held by any actual council member
3:asserting that a lack of evidence against a view is proof that the view is correct

 ### Output:


&&&&&&&&&&&&&&&&&&
### According to given context, question and choices, choose   the correct answer: 
context:
An advertisement states: Like Danaxil, all headache pills can stop your headache. But when you are in pain, you want relief right away. Danaxil is for you -- no headache pill stops pain more quickly. Evelyn and Jane are each suffering from a headache. Suppose Evelyn takes Danaxil and Jane takes its leading competitor.

question:
Which one of the following can be properly concluded from the claims in the advertisement?

choices:
0:Evelyn's headache pain will be relieved more quickly than Jane's.
1:Evelyn's headache pain will be relieved, but Jane's will not.
2:Jane will be taking Danaxil for relief from headache pain.
3:Evelyn's headache will be relieved at least as quickly as Jane's.



 ### Output:

 0
 1
 2
 3

&&&&&&&&&&&&&&&&&&

  Circulation revenue has increased by 5% in Finland. // Positive

  Panostaja did not disclose the purchase price. // Neatral

  Paying off the national debt will be extremely painful. // Negative

  The company anticipated its operating profit to improve. //  Positive

  The company's operating profit was 10% lower than expected. // Negative

  The company's operating profit was 10% lower than expected. // Negative

  The company's operating profit was 10% lower than expected. // Negative

  The company's operating profit was 10% lower than expected. // Negative

  The company's operating profit was 10% lower than expected. // Negative

  The company's operating profit was 10% lower than expected. // Negative

  The company's operating profit was 10% lower than expected. // Negative

 	省略重复

  The company's operating profit was 10%
&&&&&&&&&&&&&&&&&&

  Circulation revenue has increased by 5% in Finland. // Finance

  They defeated ... in the NFC Championship Game. // Sports

  Apple ... development of in-house chips. // Tech

  The company anticipated its operating profit to improve. // Business

  The company's ... has been affected by the pandemic. // Business

  The company's ... has been affected by the pandemic. // Business

  The company's ... has been affected by the pandemic. // Business
	省略重复
  

  The company's ... has been affected by the pandemic
```





## FT WithoutCoT Response

```

FT model without CoT
^^^^^^^^^^^~~~~~~~~~
### According to given context, question and choices, choose   the correct answer: 
context:
Council member: I recommend that the abandoned shoe factory be used as a municipal emergency shelter. Some council members assert that the courthouse would be a better shelter site, but they have provided no evidence of this. Thus, the shoe factory would be a better shelter site.

question:
A questionable technique used in the council member's argument is that of

choices:
0:accepting a claim simply because advocates of an opposing claim have not adequately defended their view
1:attacking the proponents of the courthouse rather than addressing their argument
2:attacking an argument that is not held by any actual council member
3:asserting that a lack of evidence against a view is proof that the view is correct



 ### Output:
0

 ### Explanation:
The council member's argument is that the shoe factory would be a better shelter site than the courthouse. The council member's argument is questionable because it is based on the claim that the courthouse would be a better shelter site, but the council member has not provided any evidence to support this claim.

^^^^^^^^^^^~~~~~~~~~
### According to given context, question and choices, choose   the correct answer: 
context:
An advertisement states: Like Danaxil, all headache pills can stop your headache. But when you are in pain, you want relief right away. Danaxil is for you -- no headache pill stops pain more quickly. Evelyn and Jane are each suffering from a headache. Suppose Evelyn takes Danaxil and Jane takes its leading competitor.

question:
Which one of the following can be properly concluded from the claims in the advertisement?

choices:
0:Evelyn's headache pain will be relieved more quickly than Jane's.
1:Evelyn's headache pain will be relieved, but Jane's will not.
2:Jane will be taking Danaxil for relief from headache pain.
3:Evelyn's headache will be relieved at least as quickly as Jane's.



 ### Output:
0
0
1
3

 ### Explanation:
 The advertisement states that Danaxil is for you -- no headache pill stops pain more quickly. This means that Danaxil is the only headache pill that stops pain more quickly. The advertisement also states that all headache pills can stop your headache. This means that all headache pills stop headache pain. The advertisement then states that Evelyn and Jane are each suffering from a headache. This means that Evelyn and Jane are both taking headache pills. The advertisement then states that Evelyn takes Danaxil and Jane takes its leading competitor. This means that Evelyn is taking Danaxil and Jane is taking its leading competitor. The advertisement then states that when you are in pain, you want relief right away. This means that when you are in pain, you want relief right away. The advertisement then states that Evelyn and Jane are each suffering from a headache. This means that Evelyn and Jane are both in pain. The advertisement then states that Evelyn takes Danaxil and Jane takes its leading competitor. This means that Evelyn is taking Danaxil and Jane is taking its leading competitor. The advertisement then states that when you are in pain, you want relief right away. This means that when you are in pain, you want relief right away. The advertisement then states that Evelyn and Jane are each suffering from a headache. This means that Evelyn and Jane are both in pain. The advertisement then states that Evelyn takes Danaxil and Jane takes its leading competitor. This means that Evelyn is taking Danaxil and Jane is taking its leading competitor. The advertisement then states that when you are in pain, you want relief right away. This means that when you are in pain, you want relief right away. The advertisement then states that Evelyn and Jane are each suffering from a headache. This means that Evelyn and Jane are both in pain. The advertisement then states that Evelyn takes Danaxil and Jane takes its leading competitor. This means that Evelyn is taking Danaxil and Jane is taking its leading competitor. The advertisement then states that when you are in pain, you want relief right away. This means that when you are in pain, you want relief right away. The advertisement then states that Evelyn and Jane are each suffering from a headache. This means that Evelyn and Jane are both in pain. The advertisement then states that Evelyn takes Danaxil and Jane takes its leading competitor. This means that Evelyn is taking Danaxil and Jane is taking its leading competitor. The advertisement then states that when you are in pain, you want relief right away. This means that when you are in pain, you want relief right away. The advertisement then states that Evelyn and Jane are each suffering from a headache. This means that Evelyn and Jane are both in pain. The advertisement then states that Evelyn takes Danaxil and Jane takes its leading competitor. This means that Evelyn is taking Danaxil and Jane is taking its leading competitor. The advertisement then states that when you are in pain, you want relief right away. This means that when you are in pain, you want relief right away. The advertisement then states that Evelyn and Jane are each suffering from a headache. This means that Evelyn and Jane are both in pain. The advertisement then states that Evelyn takes Danaxil and Jane takes its leading competitor. This means that Evelyn is taking Danaxil and Jane is taking its leading competitor. The advertisement then states that when you are in pain, you want relief right away. This means that when you are in pain, you want relief right away. The advertisement then states that Evelyn and Jane are each suffering from a headache. This means that Evelyn and Jane are both in pain. The advertisement then states that Evelyn takes Danaxil and Jane takes its leading competitor. This means that Evelyn is taking Danaxil and Jane is taking its leading competitor. The advertisement then states that when you are in pain, you want relief right away. This means that when you are in pain, you want relief right away. The advertisement then states that Evelyn and Jane are each suffering from a headache. This means that Evelyn and Jane are both in pain. The advertisement then states that Evelyn takes Danaxil and Jane takes its leading competitor. This means that Evelyn is taking
^^^^^^^^^^^~~~~~~~~~

  Circulation revenue has increased by 5% in Finland. // Positive

  Panostaja did not disclose the purchase price. // Neatral

  Paying off the national debt will be extremely painful. // Negative

  The company anticipated its operating profit to improve. //  Positive

  The company's operating profit was 10% higher than expected. // Positive

  The company's operating profit was 10% lower than expected. // Negative

  The company's operating profit was 10% lower than expected. // Neutral

  The company's operating profit was 10% lower than expected. // Negative

  The company's operating profit was 10% lower than expected. // Negative

  The company's operating profit was 10
^^^^^^^^^^^~~~~~~~~~

  Circulation revenue has increased by 5% in Finland. // Finance

  They defeated ... in the NFC Championship Game. // Sports

  Apple ... development of in-house chips. // Tech

  The company anticipated its operating profit to improve. // Business

  The company's stock price has increased by 10% in the past month. // Business

  The company's stock price has increased by 10% in the past month. // Business
	省略
  The company's stock price has increased
```

## FT CoT Response

```
FT model with CoT
^^^^^^^^^^^~~~~~~~~~
### According to given context, question and choices, choose   the correct answer: 
context:
Council member: I recommend that the abandoned shoe factory be used as a municipal emergency shelter. Some council members assert that the courthouse would be a better shelter site, but they have provided no evidence of this. Thus, the shoe factory would be a better shelter site.

question:
A questionable technique used in the council member's argument is that of

choices:
0:accepting a claim simply because advocates of an opposing claim have not adequately defended their view
1:attacking the proponents of the courthouse rather than addressing their argument
2:attacking an argument that is not held by any actual council member
3:asserting that a lack of evidence against a view is proof that the view is correct



 ### Output:
The council member's argument is that the shoe factory would be a better shelter site because the courthouse has not provided evidence to support its claim. This is a questionable technique because it assumes that the lack of evidence against the courthouse is proof that the shoe factory is the better shelter site. This is not a valid argument as it does not address the actual merits of the courthouse as a shelter site. Therefore, the correct answer is 0: accepting a claim simply because advocates of an opposing claim have not adequately defended their view.

^^^^^^^^^^^~~~~~~~~~
### According to given context, question and choices, choose   the correct answer: 
context:
An advertisement states: Like Danaxil, all headache pills can stop your headache. But when you are in pain, you want relief right away. Danaxil is for you -- no headache pill stops pain more quickly. Evelyn and Jane are each suffering from a headache. Suppose Evelyn takes Danaxil and Jane takes its leading competitor.

question:
Which one of the following can be properly concluded from the claims in the advertisement?

choices:
0:Evelyn's headache pain will be relieved more quickly than Jane's.
1:Evelyn's headache pain will be relieved, but Jane's will not.
2:Jane will be taking Danaxil for relief from headache pain.
3:Evelyn's headache will be relieved at least as quickly as Jane's.



 ### Output:
The advertisement states that Danaxil is for those who want relief from headache pain right away, and that it stops pain more quickly than its leading competitor.

To properly conclude from the claims in the advertisement, we need to consider the following:

- Evelyn and Jane are both suffering from headaches.
- Evelyn takes Danaxil, while Jane takes its leading competitor.
- The advertisement states that Danaxil stops pain more quickly than its leading competitor.

Based on these points, we can conclude that:

- Evelyn's headache pain will be relieved more quickly than Jane's.
- Evelyn's headache pain will be relieved, but Jane's will not.

Therefore, the correct answer is 0: Evelyn's headache pain will be relieved more quickly than Jane's.

^^^^^^^^^^^~~~~~~~~~

  Circulation revenue has increased by 5% in Finland. // Positive

  Panostaja did not disclose the purchase price. // Neatral

  Paying off the national debt will be extremely painful. // Negative

  The company anticipated its operating profit to improve. //  Positive

  The company's operating profit was 10% lower than expected. // Negative

  The company's operating profit was 10% lower than expected. // Negative
  省略

  The company's operating profit was 10%
^^^^^^^^^^^~~~~~~~~~

  Circulation revenue has increased by 5% in Finland. // Finance

  They defeated ... in the NFC Championship Game. // Sports

  Apple ... development of in-house chips. // Tech

  The company anticipated its operating profit to improve. // Business

  The company's ... in the first quarter. // Business

  The company's ... in the first quarter. // Business

  省略

  The company's ... in the first quarter. // Business

 
```



## FT Without CoT Loss



![QQ_1721094396712](https://navinvue.oss-cn-beijing.aliyuncs.com/202407160946767.png)

## FT CoT Loss

![QQ_1721094364492](https://navinvue.oss-cn-beijing.aliyuncs.com/202407160946150.png)

## Wandb Record

Wandb 没设置好，没有记录最后跑的那一次的结果...

这里附上之前跑的结果证明，微调是收敛了的（代码没证明动）

![QQ_1721102471644](https://navinvue.oss-cn-beijing.aliyuncs.com/202407161201021.png)

![QQ_1721102494169](https://navinvue.oss-cn-beijing.aliyuncs.com/202407161201867.png)