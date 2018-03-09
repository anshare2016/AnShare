# AnShare
简单实用的iOS分享，支持所有iOS版本直接分享图片和链接到微信和QQ
作者QQ 13400747421

调用方法如下：


- (IBAction)sharePicToWX:(id)sender {
    
    iOS_Share*share1 = [[iOS_Share alloc]init];                  // 创建分享对象
    [share1 init:shareWX Completeblock:^(shareResult result) {   // 调用分享对象初始化函数 shareWX 表示分享到微信，Completeblock是分享结果回调
        switch (result) {
            case shareResultCancelled:
                NSLog(@"点击取消");
                break;
            case shareResultDone:
                NSLog(@"点击分享");
                break;
        }
    }];
    
    [share1 addImage:[UIImage imageNamed:@"test.jpg"]];                                 // 添加要分享的图片
    [self presentViewController:[share1 composeVC1] animated:YES completion:nil];       // 弹出分享页面
}


- (IBAction)shareWebPageToWX11:(id)sender {
    
    iOS_Share*share1 = [[iOS_Share alloc]init];                  // 创建分享对象
    [share1 init:shareWX Completeblock:^(shareResult result) {   // 调用分享对象初始化函数 shareWX 表示分享到微信，Completeblock是分享结果回调
        switch (result) {
            case shareResultCancelled:
                NSLog(@"点击取消");
                break;
            case shareResultDone:
                NSLog(@"点击分享");
                break;
        }
    }];
    
    [share1 addUrl:[NSString stringWithFormat:@"https://www.jianshu.com/u/2910340b227e"]];                // 添加要分享的图片,这里以分享百度为例，这个函数最好找iOS11 平台调用
    [self presentViewController:[share1 composeVC1] animated:YES completion:nil];       // 弹出分享页面
}

- (IBAction)shareWebPageToWX:(id)sender {
    
    iOS_Share*share1 = [[iOS_Share alloc]init];                  // 创建分享对象
    [share1 init:shareWX Completeblock:^(shareResult result) {   // 调用分享对象初始化函数 shareWX 表示分享到微信，Completeblock是分享结果回调
        switch (result) {
            case shareResultCancelled:
                NSLog(@"点击取消");
                break;
            case shareResultDone:
                NSLog(@"点击分享");
                break;
        }
    }];
    
    // 分享链接到任意iOS平台,这里可以指定链接显示的图片和标题
    [share1 addUrl:[NSString stringWithFormat:@"http://www.baidu.com"] Title:@"my modify title" Image:[UIImage imageNamed:@"test.jpg"]];
    [self presentViewController:[share1 composeVC1] animated:YES completion:nil];            // 弹出分享页面
}


- (IBAction)sharePicToQQ:(id)sender {
    
    iOS_Share*share1 = [[iOS_Share alloc]init];                  // 创建分享对象
    [share1 init:shareQQ Completeblock:^(shareResult result) {   // 调用分享对象初始化函数 shareWX 表示分享到微信，Completeblock是分享结果回调
        switch (result) {
            case shareResultCancelled:
                NSLog(@"点击取消");
                break;
            case shareResultDone:
                NSLog(@"点击分享");
                break;
        }
    }];
    
    [share1 addImage:[UIImage imageNamed:@"test.jpg"]];                                 // 添加要分享的图片
    [self presentViewController:[share1 composeVC1] animated:YES completion:nil];       // 弹出分享页面
}

- (IBAction)shareWebPageToQQ:(id)sender {
    iOS_Share*share1 = [[iOS_Share alloc]init];                  // 创建分享对象
    [share1 init:shareQQ Completeblock:^(shareResult result) {   // 调用分享对象初始化函数 shareWX 表示分享到微信，Completeblock是分享结果回调
        switch (result) {
            case shareResultCancelled:
                NSLog(@"点击取消");
                break;
            case shareResultDone:
                NSLog(@"点击分享");
                break;
        }
    }];
    
    [share1 addUrl:[NSString stringWithFormat:@"https://www.jianshu.com/u/2910340b227e"]];
    [self presentViewController:[share1 composeVC1] animated:YES completion:nil];       // 弹出分享页面
}

