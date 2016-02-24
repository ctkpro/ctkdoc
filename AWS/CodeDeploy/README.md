# 一些 CodeDeploy的使用心得

- [如何設定EC2的role，讓EC2可以被CodeDeploy deploy code](#set_ec2_role)
- [如何設定CodeDeploy本身要用的role](#set_codedeploy_role)
- [Create New CodeDeploy Application](#create_codedeploy_application)
- [Create New Deployment](#create_codedeploy_deployment)

<a name="set_ec2_role"></a>
### 如何設定EC2的role，讓EC2可以被CodeDeploy deploy code
1. create一個role
![create role](https://cloud.githubusercontent.com/assets/6972644/13244092/9f80dc4e-da3e-11e5-8f19-e69144b19939.jpg)

2. 選擇 **Amazon EC2** 
![choose Amazon EC2](https://cloud.githubusercontent.com/assets/6972644/13244239/abae4dd4-da3f-11e5-990b-801215ba01aa.jpg)

3. 選擇 **AWSCodeDeployRole**
![choose AWSCodeDeployRole](https://cloud.githubusercontent.com/assets/6972644/13244245/b632bc04-da3f-11e5-9e2d-a1a692c020a0.jpg)

4. 在launch EC2的時候要選擇剛剛建立的role
![select role](https://cloud.githubusercontent.com/assets/6972644/13244508/b36a4828-da41-11e5-9bc9-3fee972fd864.jpg)

<a name="set_codedeploy_role"></a>
### 如何設定CodeDeploy本身要用的role
1. 按下 **Create New Role**
![1](https://cloud.githubusercontent.com/assets/6972644/13245098/c175cd1c-da45-11e5-81ba-f64bf5099740.jpg)

2. 在 **AWS Service Roles** 下面選擇 **AWS CodeDeploy**
![2](https://cloud.githubusercontent.com/assets/6972644/13245099/c176636c-da45-11e5-8f47-91863a820f7f.jpg)

3. 選擇 **AWSCodeDeployRole**
![3](https://cloud.githubusercontent.com/assets/6972644/13245100/c1772bd0-da45-11e5-8003-46e535d0cae0.jpg)

<a name="create_codedeploy_application"></a>
### Create New CodeDeploy Application
1. 選擇 **Custom Deployment**
![1](https://cloud.githubusercontent.com/assets/6972644/13245227/c3cdf67e-da46-11e5-9f1e-322b9acc1c46.jpg)

2. 填好對應資料，注意此EC2的Name必須要為存在的ec2 instance，不能隨便亂給
![2](https://cloud.githubusercontent.com/assets/6972644/13245229/c3d26dd0-da46-11e5-811e-f9306a012aaa.jpg)

3. Service role要選擇在[[如何設定CodeDeploy本身要用的role](#set_codedeploy_role)]裡設定好的role
![3](https://cloud.githubusercontent.com/assets/6972644/13245228/c3cf03e8-da46-11e5-8613-513d1af48549.jpg)

<a name="create_codedeploy_deployment"></a>
### Create New Deployment
1. Select **Deploy new revision**
![1](https://cloud.githubusercontent.com/assets/6972644/13245860/0cc9c944-da4b-11e5-802c-466ef3b40e43.jpg)

2. 填入相關資訊，按下 **Connect Github**
![2](https://cloud.githubusercontent.com/assets/6972644/13245862/0cca6d04-da4b-11e5-85b4-fa42763c998b.jpg)

> commit ID為你想要deploy的那個版本的commit ID，可到github複制 
> ![copy commit id](https://cloud.githubusercontent.com/assets/6972644/13275226/84b73598-daed-11e5-9686-6e338e929129.jpg)

3. 填入相關資訊
![3](https://cloud.githubusercontent.com/assets/6972644/13245861/0cca3596-da4b-11e5-99b1-18b22a4d2ac4.jpg)
