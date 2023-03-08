---
title: Pull requests（简称PR）
---

:::tip 提示
本内容默认已完成[5.通过Github共创](../p0/p0-5-collaborate.md)：
1. 安装Git
2. Git的初始配置
3. 为Github配置SSH登录
4. 将共创共学仓库Fork到自己的GitHub账户
5. 从自己的Github克隆仓库拉到本地
6. 在本地修改了内容
7. 将本地内容提交到自己的Github克隆仓库

补充Pull Request的几个场景及处理方案。

:::info 信息
共创共学原仓库：programming-co_creation-docs
你在原仓库点击Fork按键同步到自己的GitHub账户里的克隆仓库：programming-co_creation-docs(没改名的情况下与原仓库同名，若更改过名的是改名后的名称)
本地仓库：文件夹名称programming-co_creation-docs或你改名后的名称，可用VScode打开

#### 常规步骤：
请新手在本地仓库编辑了内容之后，为了避免遇到现阶段无法自行解决的更复杂情况，务必严格在`Terminal`（终端）按以下步骤执行：
1. `git status` 检查本地是否有未提交的修改（修改的未提交管理的文件名颜色是红色）
2. `git add .`将本地已变更的文件提交给git管理
3. `git status` 检查上一步操作是否提交成功（修改的文件名颜色由红色变成绿色）
4.  `git commit -m 'your update name'`将所有更新的内容做为一个完整的存档版本准备提交到原仓库合并（your update name是这次存档的命名，例如update p1-3 ide，可在本地进行多次`git commit`得到最终满意的版本后再提交RP）
5. `git status`再次检查是否还有没存档的内容（无文件提交，干净的工作区）
6. `git push` 把本地仓库已存档版本向自己的GitHub账户里的克隆仓库推送本地的修改内容

以上步骤完成，即实现了本地仓库与克隆仓库的内容同步。
![Alt text](Pull%20requests.assets/Xnip2023-03-02_18-43-11.jpg)

![Alt text](Pull%20requests.assets/Xnip2023-03-02_18-44-44.jpg)

![Alt text](Pull%20requests.assets/Xnip2023-03-02_18-45-24.jpg)


建议新手多次重复以上操作步骤进行练习，不用担心将本地仓库和克隆仓库的内容"玩乱"了......因为我们有一个简单直接的方法恢复——删除克隆仓库和本地仓库，在共创共学原仓库重新Fork。

当然，这个简单直接的方法仅作为新手练习阶段或后期出现了太复杂的局面实在无办法处理的情况下的最后选择。

#### 删除克隆仓库
1. 进入自己的GitHub账户里的克隆仓库，点击`Setting`，进入General项目的常规设置界面

![Alt text](Pull%20requests.assets/Xnip2023-03-01_10-13-25.jpg)

2. 在常规设置界面一直往下拉到最后的Danger Zone危险区，点击 `Delete this repository`删除此仓库

![Alt text](Pull%20requests.assets/Xnip2023-03-01_10-13-52.jpg)


3. 弹出确认窗口，需要在蓝色框内输入需要删除的仓库的账号和名称。（可复制蓝色框上一行加粗内容，如Ayan0217/programming-co_creation-docs）

![Alt text](Pull%20requests.assets/Xnip2023-03-01_10-14-31.jpg)

4. 当蓝色框下面的`I understand the consequences, delete this repository`变成红色可点击时，点击此按键会提示输入GitHub账户的Password密码，输入密码后点击`Confirm`确认，即完成删除此仓库。

![Alt text](Pull%20requests.assets/Xnip2023-03-01_10-15-19.jpg)


#### 场景一：
首次Fork原仓库创建了自己账号下的克隆仓库，并通过SSH克隆到本地，此时共创共学原仓库、克隆仓库和本地仓库，三个仓库可视为完全同步状态。

本地仓库编辑后完成了常规步骤(见上文)

这时共创共学原仓库与克隆仓库的差异是本地仓库编辑过的内容，我们只需要向原仓库提交一次Pull requests，请求原仓库同意merge合并变更的内容。

1. 进入自己的GitHub账户里的克隆仓库，点击`Pull requests`进入PR界面，点击绿色按键`New pull request`系统会自动对比差异。

![Alt text](Pull%20requests.assets/Xnip2023-03-08_08-38-20.jpg)

2. 确认信息
左边是共创共学原仓库，右边是你自己的GitHub账户里的变更过的克隆仓库

![Alt text](Pull%20requests.assets/Xnip2023-03-08_08-45-55.jpg)

3. 确认`Pull requests`

4. 已完成提交，等待共创共学原仓库管理员审核内容并同意merge合并。

![Alt text](Pull%20requests.assets/Xnip2023-03-02_18-49-57.jpg)

#### 场景二：
克隆仓库和本地仓库已存在一段时间，首先需要确认共创共学原仓库、克隆仓库和本地仓库，三个仓库是否完全同步。

1. 进入自己的GitHub账户里的克隆仓库，点击`Sync fork`的小三角，可以看到提示更新此克隆仓库，原因是原仓库有更新，点击`Update branch`


![Alt text](Pull%20requests.assets/Xnip2023-03-08_13-14-48.jpg)

2. 再次点击`Sync fork`的小三角，可以看到提示此克隆仓库与原仓库是同步的了。

![Alt text](Pull%20requests.assets/Xnip2023-03-08_13-30-38.jpg)

3. 在`Terminal`（终端）输入命令`git pull`将本地的仓库更新

![Alt text](Pull%20requests.assets/Xnip2023-03-08_13-38-46.jpg)


 此时共创共学原仓库、克隆仓库和本地仓库，三个仓库可视为完全同步状态。
 
 即回到了场景一的那一套操作：在`Terminal`（终端）输入命令`code .`打开本地仓库，在VSCode中进行编辑，编辑完成后，在`Terminal`（终端）完成常规步骤将本地仓库的更新`git push`到自己的GitHub克隆仓库，在GitHub账户里点击`New pull request`提交变更内容，等待审核merge合并。

很不巧，在你的本地仓库编辑内容期间，有其他共创成员给原仓库提交了`Pull requests`且PR被主仓库merge合并了。

此时原仓库已静悄悄地更新了，然而你的克隆仓库与本地仓库并没有更新，三个仓库并不是你原本以为的完全同步......

当点击`Pull requests`时，会提示有冲突，需要解决。

请MUMU帮忙制造这个场景。提交一个新的PR

#### 场景三：
本地仓库编辑内容期间，有其他共创成员给原仓库提交了`Pull requests`且修改的文件与你本地仓库编辑的文件是相同的文件，且PR被主仓库merge合并了。

点击`Pull requests`时，会提示有冲突，需要解决。

请MUMU帮忙制造这个场景。删除这一句话修改此文档提交PR，merge和不merge都来一遍？


#### 其他场景待补充