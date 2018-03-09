# AnShare
简单实用的iOS分享，支持所有iOS版本直接分享图片和链接到微信和QQ

作者QQ 919174554   未经授权，不得用于商业用途，否则后果自负

调用方法如下：

    iOS_Share*share1 = [[iOS_Share alloc]init];
    
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
    
    [share1 addImage:[UIImage imageNamed:@"test.jpg"]];
    
    [self presentViewController:[share1 composeVC1] animated:YES completion:nil];
