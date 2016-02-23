# 一些 CodeDeploy的使用心得

### 如何設定EC2的role，讓EC2可以被CodeDeploy deploy code
1. create一個role
![create role](https://cloud.githubusercontent.com/assets/6972644/13244092/9f80dc4e-da3e-11e5-8f19-e69144b19939.jpg)

2. 選擇 **Amazon EC2** 
![choose Amazon EC2](https://cloud.githubusercontent.com/assets/6972644/13244239/abae4dd4-da3f-11e5-990b-801215ba01aa.jpg)

3. 選擇 **AWSCodeDeployRole**
![choose AWSCodeDeployRole](https://cloud.githubusercontent.com/assets/6972644/13244245/b632bc04-da3f-11e5-9e2d-a1a692c020a0.jpg)

4. 在launch EC2的時候要選擇剛剛建立的role
![select role](https://cloud.githubusercontent.com/assets/6972644/13244508/b36a4828-da41-11e5-9bc9-3fee972fd864.jpg)