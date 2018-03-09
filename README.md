# AnShare
简单实用的iOS分享，支持所有iOS版本直接分享图片和链接到微信和QQ
作者QQ 13400747421

调用方法如下：

- (IBAction)sharePicToWX:(id)sender {
    
    // 创建分享对象
    iOS_Share*share1 = [[iOS_Share alloc]init];
    
    // 调用分享对象初始化函数 shareWX 表示分享到微信，Completeblock是分享结果回调
    [share1 init:shareWX Completeblock:^(shareResult result) {
        switch (result) {
            case shareResultCancelled:
                NSLog(@"点击取消");
                break;
            case shareResultDone:
                NSLog(@"点击分享");
                break;
        }
    }];
    
     // 添加要分享的图片
    [share1 addImage:[UIImage imageNamed:@"test.jpg"]];
    
    // 弹出分享页面
    [self presentViewController:[share1 composeVC1] animated:YES completion:nil];
}
