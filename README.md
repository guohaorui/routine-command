# routine-command  
常用linux命令  
查看当前登录用户：w  
查看显卡使用情况：nvidia-smi  
指定显卡：CUDA_VISIBLE_DEVICES=0    python  your_file.py  
挂起进程：nohup /root/start.sh > output.txt &  
挂起进程训练模型：CUDA_VISIBLE_DEVICES=1 nohup python networkTraining.py Config.ini 0 > ./training_results/1_19_training.txt &    
利用训练好的权重分割: CUDA_VISIBLE_DEVICES=1 nohup python networkSegmentation.py FCN_Segmentation.ini /home/haorui/plaque/FCN3D/outputFiles/FCN_Test_Fold_1_16_1/Networks/FCN_Epoch36 > ./segmenting_results/1_16_testing_add.txt &  
查看当前目录下的文件及其容量 du sh

# nii图片处理
# python
import nibabel as nib  
import numpy as np  
np.shape(ni.load('file.nii').get_data())--> result: (320,320,240) from 'dengyixin.nii'   
oriImage = nib.load('file.nii')  
gtImage = nib.load('gt_file.nii')  
changedGtImage = nib.Nifti1Image(gtImage.get_data(), orgImage.affine)  
nib.save(changedGtImage,'gt_file_changed.nii')  
# matlab
导入NIfTI_20140122包  
imagePath = 'D:\plaque\code\Training_data_p\imagesFolder\';  
gtPath = 'D:\plaque\code\Training_data_p\GroundTruthFolder\';  
imageName = [imagePath, 'mahanquan.nii']  
gtName = [gtPath, 'mahanquanp.nii']  
gtImage = load_untouch_nii(gtName);  
gtData = gtImage.img;  
gtData = gtData(:,end:-1:1,:);  
% gtData = gtData(:,:,end:-1:1);  
changeGt = make_nii(gtData, [], [], 4);  
save_nii(changeGt, [gtPath, 'mahanquanp-change.nii']);  


# basic operation  
查看隐藏文件：ls -la  
创建文件：touch file
修改文件：echo "test" >> file
查看文件夹大小：du -h 路径

# matlab command  
set(gcf,'position',[200,200,500,400]); 一张图片最佳宽为500，高为400


# git command  
Git初始化：
$ git config --global user.name "Scott Chacon"
$ git config --global user.email "schacon@gmail.com"
初始化新仓库  
mkdir project  
cd project  
git init  
查看git仓库状态  
git status  
把文件加入缓存区  
git add file  
使用git commit 提交修改, 文件会被提交到本地仓库  
git commit -m "add file"--> -m添加comment
