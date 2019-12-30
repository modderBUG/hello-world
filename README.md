# hello-world
/*none*/
# Hello World 项目是计算机编程中历史悠久的传统。 这是一个简单的练习，可以让你在学习新东西时开始学习。 让我们开始使用GitHub！
您将学习如何：
+ Create and use a repository 创建和使用存储库)
+ Start and manage a new branch 启动并管理新分支)
+ Make changes to a file and push them to GitHub as commits 对文件进行更改并将其作为提交推送到GitHub)
+ Open and merge a pull request  打开并合并拉取请求）



## 什么是GitHub？
+ GitHub是用于版本控制和协作的代码托管平台。 它可以让您和其他人在任何地方协同工作。
+ 本教程教您GitHub基本知识，如存储库，分支，提交和Pull请求(repositories, branches, commits, and Pull Requests)。 您将创建自己的Hello World存储库并学习GitHub的Pull Request工作流，这是一种创建和检查代码的流行方法。
+ 无需编码
+ 要完成本教程，您需要GitHub.com帐户和Internet访问权限。 您不需要知道如何编码，使用命令行或安装Git（基于版本控制软件GitHub）。

```
提示：在单独的浏览器窗口（或选项卡）中打开本指南，以便在完成本教程中的步骤时看到它。
```




## 步骤1.创建存储库(Repository)
 - 存储库通常用于组织单个项目。 存储库可以包含文件夹和文件，图像，视频，电子表格和数据集 - 您的项目需要的任何内容。 我们建议包括README或包含项目信息的文件。 GitHub可以在创建新存储库的同时轻松添加一个。 它还提供其他常见选项，例如许可证文件。
 - 您的hello-world存储库可以是您存储想法，资源，甚至与他人共享和讨论事物的地方。

 创建新repository
 1. 在右上角，在您的头像或identicon旁边，单击，然后选择 New repository.
 2. 命名您的存储库（repository） hello-world.
 3. 写一个简短的描述。
 4. Select Initialize this repository with a README.
 点击 Create repository. 


## 步骤2. 创建一个分支(Branch)
+ 分支(Branch)是一次处理不同版本的存储库的方法。
+ 默认情况下，您的存储库有一个名为master的分支，它被认为是权威分支。 在将它们提交给master之前，我们使用分支进行实验并进行编辑。
+ 当您从主分支创建分支时，您正在制作主服务器的副本或快照，就像在那个时间点那样。 如果其他人在您的分支上工作时对主分支进行了更改，则可以引入这些更新。

###该图显示：
# 主分支
# 一个叫做feature的新分支（因为我们在这个分支上做'feature work'）
# 功能在合并到主服务器之前所经历的旅程



### 你有没有保存过不同版本的文件？ 就像是：
+ story.txt
+ story-joe-edit.txt
+ story-joe-edit-reviewed.txt
- 分支机构在GitHub存储库中实现了类似的目标。
- 在GitHub，我们的开发人员，编写人员和设计人员使用分支来保持错误修复和功能工作与主（生产）分支分开。 当更改准备就绪时，它们将其分支合并到主服务器中。

### 创建一个新分支（branch）
5. 转到新的存储库 hello-world.
6. 单击文件列表顶部的下拉列表 branch: master.
7. 输入分支名称, readme-edits,入新的分支文本框.
8. 选择蓝色的Create branch框或按键盘上的“Enter”


### 现在你有两个分支，master and readme-edits。 它们看起来完全一样，但不会很久！ 接下来，我们将更改添加到新分支。

## 步骤3. 制作并提交更改
好样的！ 现在，您正在阅读readme-edits branch的代码视图，该分支是master的副本。 我们来做一些编辑。
在GitHub上，保存的更改称为提交。 每个提交都有一个关联的提交消息，这是一个解释为什么进行特定更改的描述。 提交消息可捕获更改的历史记录，因此其他贡献者可以了解您已完成的操作以及原因。

### 制作并提交更改
9. 点击 README.md 文件.
10. 单击文件视图右上角的铅笔图标进行编辑.
11. 在编辑器中，写下一些关于你自己的文章.
12. 编写描述更改的提交消息.
13. 点击 Commit changes 按钮.


这些更改将仅对readme-editsbranch上的README文件进行，因此现在该分支包含的内容与master不同。

## 步骤4.打开Pull Request

很好！ 现在您在master的分支中有更改，您可以打开pull Request。

Pull Requests是GitHub上合作的核心。 当您打开拉取请求时，您提出了更改并请求某人审核并提取您的贡献并将其合并到他们的分支中。 拉请求显示来自两个分支的内容的差异或差异。 更改，添加和减少以绿色和红色显示。

提交后，即使在代码完成之前，您也可以打开拉取请求并开始讨论。

通过在拉取请求消息中使用GitHub的 @mention system系统，您可以询问特定人员或团队的反馈，无论他们是在大厅还是10个时区之外。

您甚至可以在自己的存储库中打开pull请求并自行合并。 在开展大型项目之前，这是学习GitHub流程的好方法。

打开Pull Request以更改README

点击图像查看大图  并么有

Step	Screenshot

单击Pull Request选项卡，然后从Pull Request页面中，单击绿色New pull request按钮。	

In the Example Comparisons box, select the branch you made, readme-edits, to compare with master (the original).	

在“Example Comparisons”框中，选择您创建的分支，自述编辑，以与主（原始）进行比较。

Look over your changes in the diffs on the Compare page, make sure they’re what you want to submit.	

在比较页面上查看差异中的差异，确保它们是您要提交的内容。

When you’re satisfied that these are the changes you want to submit, click the big green Create Pull Request button.	

如果您对要提交的更改感到满意，请单击绿色的“Create Pull Request”按钮。

Give your pull request a title and write a brief description of your changes.	

为您的拉取请求提供标题，并写下您的更改的简要说明。

来自 <https://guides.github.com/activities/hello-world/> 

完成后，单击  Create pull request!

Tip: You can use emoji and drag and drop images and gifs onto comments and Pull Requests.

提示：您可以使用表情符号并将图像和GIF拖放到注释和请求上。

### 步骤5.合并您的Pull请求

在最后一步中，是时候将您的更改结合在一起 - 将您的readme-edits branch合并到master branch.

14. 单击绿色 Merge pull request按钮以将更改合并到 master.
15. 点击 Confirm merge.
16. 继续删除分支，因为它的更改已合并，紫色框中的 Delete branch按钮。



Celebrate!

通过完成本教程，您已经学会了创建一个项目并在GitHub上发出拉取请求！
		

	
 
 
以下是您在本教程中完成的内容：

+ 创建了一个开源存储库 repository
+ 开始并管理一个新的分支 branch
+ 更改了文件并将这些更改提交给GitHub
+ 打开并合并了一个Pull Request

看看你的GitHub个人资料，你会看到你的新贡献正方形 contribution squares!

要了解有关Pull Requests功能的更多信息，我们建议您阅读GitHub流程指南 GitHub flow Guide。 您也可以访问 GitHub Explore并参与开源项目


提示：查看我们的其他指南，YouTube频道和按需培训，了解有关如何开始使用GitHub的更多信息。






