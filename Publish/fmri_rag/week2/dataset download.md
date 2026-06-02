```
#!/bin/bash

# 设置基础路径
BASE_S3="s3://openneuro.org/ds005165/derivatives/versionB/fsaverage/GLM"
BASE_LOCAL="/Users/jackpeng/Desktop/BOLD-Moments-Dataset/derivatives/versionB/fsaverage/GLM"

# 下载文本标注文件
echo "=========================================="
echo "下载文本标注文件 annotations.json"
echo "=========================================="
mkdir -p /Users/jackpeng/Desktop/BOLD-Moments-Dataset/derivatives/stimuli_metadata
aws s3 cp --no-sign-request \
    "s3://openneuro.org/ds005165/derivatives/stimuli_metadata/annotations.json" \
    "/Users/jackpeng/Desktop/BOLD-Moments-Dataset/derivatives/stimuli_metadata/annotations.json"

# 循环下载 10 个被试的核心文件
for i in $(seq -f "%02g" 1 10); do
    echo ""
    echo "=========================================="
    echo "正在下载 sub-$i 的核心数据..."
    echo "=========================================="
    
    # 创建目标文件夹
    mkdir -p "$BASE_LOCAL/sub-$i/prepared_betas"
    
    # 下载训练集（左半球 + 右半球）
    echo "下载 sub-$i 训练集..."
    aws s3 cp --no-sign-request \
        "$BASE_S3/sub-$i/prepared_betas/sub-${i}_organized_betas_task-train_hemi-left_normalized.pkl" \
        "$BASE_LOCAL/sub-$i/prepared_betas/"
    
    aws s3 cp --no-sign-request \
        "$BASE_S3/sub-$i/prepared_betas/sub-${i}_organized_betas_task-train_hemi-right_normalized.pkl" \
        "$BASE_LOCAL/sub-$i/prepared_betas/"
    
    # 下载测试集（左半球 + 右半球）
    echo "下载 sub-$i 测试集..."
    aws s3 cp --no-sign-request \
        "$BASE_S3/sub-$i/prepared_betas/sub-${i}_organized_betas_task-test_hemi-left_normalized.pkl" \
        "$BASE_LOCAL/sub-$i/prepared_betas/"
    
    aws s3 cp --no-sign-request \
        "$BASE_S3/sub-$i/prepared_betas/sub-${i}_organized_betas_task-test_hemi-right_normalized.pkl" \
        "$BASE_LOCAL/sub-$i/prepared_betas/"
    
    echo "sub-$i 下载完成"
done

echo ""
echo "=========================================="
echo "所有数据下载完成！"
echo "=========================================="
echo ""
echo "文件保存在: /Users/jackpeng/Desktop/BOLD-Moments-Dataset/"
echo ""
echo "验证下载结果:"
echo "  ls -la /Users/jackpeng/Desktop/BOLD-Moments-Dataset/derivatives/versionB/fsaverage/GLM/sub-01/prepared_betas/"
echo "  ls -la /Users/jackpeng/Desktop/BOLD-Moments-Dataset/derivatives/stimuli_metadata/"
```