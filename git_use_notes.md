### 本地还原修改的做法：
    git reset --hard HEAD
    然后git checkout 文件名。或者直接git checkout 对应文件名

  git checkout -- file:撤销对工作区修改；这个命令是以最新的存储时间节点（add和commit）为参照，覆盖工作区对应文件file；这个命令改变的是工作区
  
  git reset HEAD -- file:清空add命令向暂存区提交的关于file文件的修改（Ustage）；这个命令仅改变暂存区，并不改变工作区，这意味着在无任何其他操作的情况    下，工作区中的实际文件同该命令运行之前无任何变化
  
  HEAD：对应状态的上一个提交
  
  
  ### 根据–soft –mixed –hard，会对working tree和index和HEAD进行重置:
    git reset --mixed：此为默认方式，不带任何参数的git reset，即时这种方式，它回退到某个版本，只保留源码，回退commit和index信息

    git reset --soft：回退到某个版本，只回退了commit的信息，不会恢复到index file一级。如果还要提交，直接commit即可
    
    Git reset  --hard：彻底回退到某个版本，本地的源码也会变为上一个版本的内容，此命令 慎用！
