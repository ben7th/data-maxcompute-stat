这里是医学统计的基本需求：
## 1、用药、治疗的统计：
统计近一段时间（可设定）的history和monitor的有效性、副作用比例；
数据来源：
```
ug_ing.purpose.effectiveness[..]中任何一个症状或疾病>0即认为有效。
drug_ing.side_effects.degree[..]中任何一个症状或疾病>0即认为有作用。
drug_history.purpose.effectiveness[..]中任何一个症状或疾病>0即认为有效。
drug_history.side_effects.degree[..]中任何一个症状或疾病>0即认为有作用。
```
有效性结果集：
```
sym_id:症状id
p_major: 明显人数
p_moderate:有用人数
p_slight：有一点点用的人数
p_none：无用人数
p_cant：不确定
methol_type:方法的类型药品、治疗
method_id ：药品或治疗的bmesh
total:总人数
```
副作用结果集：
```
sym_id:症状id
s_severe：症状严重人数
s_mid：症状中等人数
s_mederate：症状轻微人数
methol_type:方法的类型药品、治疗
method_id ：药品或治疗的bmesh
total:总人数
```
治疗类同
## 2、疾病和症状的关联性统计
```
sym_id:症状id
disease_id:疾病的bmesh
p_major: 主要症状比例
p_moderate:一般比例
p_slight：轻度比例
p_None：无
p_cant：不确定
total：总人数
```
xxx疾病与xxx症状的关联性，给出疾病的bmesh可以给出排名前n位的症状；
## 3、症状严重程度的分布
```
sym_id:症状id
s_severe：症状严重人数
s_mid：症状中等人数
s_mederate：症状轻微人数
total：总人数
```
## 4、疾病的人群分布
 性别、年龄
## 5、疾病与用药和治疗的关系统计
```
type:方法的类型药品、治疗
disease_id: 疾病的bmesh
sym_id:症状id
p_major: 主要症状人数
p_moderate:一般症状人数
p_slight：轻度症状人数
p_none：无症状人数
p_cant：不确定
method_id ：药品或治疗的bmesh
s_severe：症状严重人数
s_mid：症状中等人数
s_mederate：症状轻微人数
s_none：症状无人数
Perceived_effectiveness：感知有效性人数
total：总人数
```

参考，plm的type有（我们暂时不用）：
```
Prescription Drug 处方药
Physical Therapy 物理治疗
Psychotherapy 心理治疗
Over the Counter Drug 非处方药
Other 其他
Supplement  其他
Procedures
Equipment 设备
Lifestyle Modification 生活方式的改变
Nutrition/Diet  营养/饮食
Surgery  外科
Exercise 运动
Complementary and Alternative Medicine  补充和替代医学

```
## 6、症状与treat的关联性统计
```
sym_id:症状id
method_id:方法的bmesh
type:方法的类型药品、治疗
patients：人数
```
