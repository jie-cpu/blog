#!/bin/bash

BASE_S3="s3://openneuro.org/ds005165"
BASE_LOCAL="/Users/jackpeng/Desktop/BOLD-Moments-Dataset"

echo "=========================================="
echo "为每个 subject 下载两个 organized_betas 文件"
echo "=========================================="

for sub in sub-01 sub-02 sub-03 sub-04 sub-05 sub-06 sub-07 sub-08 sub-09 sub-10; do
    echo ""
    echo ">>> ${sub}"
    
    # 创建本地目录
    mkdir -p "${BASE_LOCAL}/derivatives/versionB/MNI152/GLM/${sub}/prepared_betas/"
    
    # 下载训练集文件
    aws s3 cp --no-sign-request \
        "${BASE_S3}/derivatives/versionB/MNI152/GLM/${sub}/prepared_betas/${sub}_organized_betas_task-train_normalized.pkl" \
        "${BASE_LOCAL}/derivatives/versionB/MNI152/GLM/${sub}/prepared_betas/" \
        2>/dev/null && echo "  ✓ 训练集已下载" || echo "  ✗ 训练集不存在"
    
    # 下载测试集文件
    aws s3 cp --no-sign-request \
        "${BASE_S3}/derivatives/versionB/MNI152/GLM/${sub}/prepared_betas/${sub}_organized_betas_task-test_normalized.pkl" \
        "${BASE_LOCAL}/derivatives/versionB/MNI152/GLM/${sub}/prepared_betas/" \
        2>/dev/null && echo "  ✓ 测试集已下载" || echo "  ✗ 测试集不存在"
done

echo ""
echo "=========================================="
echo "✅ 下载完成！"
echo "=========================================="
echo ""
echo "最终目录结构："
echo "derivatives/versionB/MNI152/GLM/"
echo "├── sub-01/prepared_betas/"
echo "│   ├── sub-01_organized_betas_task-train_normalized.pkl"
echo "│   └── sub-01_organized_betas_task-test_normalized.pkl"
echo "├── sub-02/prepared_betas/"
echo "│   └── ..."
echo "└── sub-10/prepared_betas/"
echo "    └── ..."