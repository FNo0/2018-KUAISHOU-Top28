# 中国高校计算机大赛-大数据挑战赛（复赛28，初赛A:1，初赛B:2）
初赛评价指标F1，该单模型A榜0.822173，B榜0.819342。和队友融合A榜达到0.822788，B榜达到0.81985。初赛模型一直比较稳，但这也是最后的辉煌了。没有特别关注阈值，AB榜都一直提交的前25000个。
复赛换了auc一直做不上去，我也不知道为什么，最终28名，很遗憾。这里就只分享我初赛的方案。

model_1这套方案采用的划窗方式是每一天向前滑：
train1:用户1-18，历史信息1-18，标签19-25；
train2:用户1-19，历史信息2-19，标签20-26；
train3:用户1-20，历史信息3-20，标签21-27；
train4:用户1-21，历史信息4-21，标签22-28；
train5:用户1-22，历史信息5-22，标签23-29；
train6:用户1-23，历史信息6-23，标签24-30；
test:用户1-30，历史信息13-30。

model_3这套方案采用标签不重叠的划窗：
train1:用户1-9，历史信息1-9，标签10-16；
train2:用户1-16，历史信息8-16，标签17-23；
train3:用户1-23，历史信息15-23，标签24-30；
test:用户1-30，历史信息22-30。

两套方案特征相同。