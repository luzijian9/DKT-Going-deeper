# DKT-Going-deeper
reconstruct the model of deep knowledge tracing

the code from：https://github.com/siyuanzhao/2016-EDM

you can see some details on his page or his paper "Going Deeper with Deep Knowledge Tracing"

his environment：

TensorFlow 0.10

scikit-learn

I reproduce this code by TensorFlow 0.12.1，since the 'pip' can only install this version

the input shape ：[ batch, num_problem] ，the value represent the information of skills which are answered by each student。

but the author reshape the input to 1-D vector， then compute the deviation the logits and label.

the other job I done is the convert the version of tensorflow, 0.12.1 to 1.15.2.

I run the code in google colab, but I can't solve the bug about tf.flags. 

Because jupyter will save the memory, so it will raise the error
```python
The flag ‘f’ is defined twice. First from /home/huanghanchi/anaconda3/lib/python3.7/site-packages/ipykernel_launcher.py, Second from /home/huanghanchi/anaconda3/lib/python3.7/site-packages/ipykernel_launcher.py. Description from first occurrence: kernel
```
two version has this problem, the solution is restart the kernel. it wastes me two hours, what's worse,I have to solve the compatibility of two tf version

parameter： batchsize：32 Hidden layer size: 200 

TensorFlow0.12.1 used cpu 19minute per epoch

TensorFlow1.15.2 used gpu—Tesla 40second per epoch

amazing!!!

Epoch: 2 Test Metrics:

 rmse: 0.399 	 auc: 0.809 	 r2: 0.294
 
Epoch: 5 Test Metrics:

 rmse: 0.397 	 auc: 0.816 	 r2: 0.299
 
Epoch: 8 Test Metrics:

 rmse: 0.394 	 auc: 0.818 	 r2: 0.308

Epoch: 10 Train Metrics:

 rmse: 0.387 	 auc: 0.835 	 r2: 0.337 
 
 note: DKT-2016 tf 0.12.1
       DKT tf 1.15.2
       
a :Has subproblems

b :Repeat sequnces for mutiple skills

c :Combined skills for mutiple skills
