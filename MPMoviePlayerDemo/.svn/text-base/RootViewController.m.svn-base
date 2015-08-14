//
//  RootViewController.m
//  MPMoviePlayerDemo
//
//  Created by fq on 15/8/12.
//  Copyright (c) 2015年 fangqian. All rights reserved.
//

#import "RootViewController.h"
#import "CustomViewController.h"
#import <MediaPlayer/MediaPlayer.h>

@interface RootViewController ()

@end

@implementation RootViewController

- (void)viewDidLoad {
    [super viewDidLoad];
    
    UIButton * button =[UIButton buttonWithType:UIButtonTypeCustom];
    [button setTitle:@"播放" forState:UIControlStateNormal];
    [button setTitleColor:[UIColor redColor] forState:UIControlStateNormal];
    button.frame=CGRectMake(100, 320, 100, 100);
    [button addTarget:self action:@selector(buttonClicked) forControlEvents:UIControlEventTouchUpInside];
    [self.view addSubview:button];
    
    
    
    UIButton * button1 =[UIButton buttonWithType:UIButtonTypeCustom];
    [button1 setTitle:@"横屏" forState:UIControlStateNormal];
    [button1 setTitleColor:[UIColor greenColor] forState:UIControlStateNormal];
    button1.frame=CGRectMake(200, 320, 100, 100);
    [button1 addTarget:self action:@selector(btnClicked) forControlEvents:UIControlEventTouchUpInside];
    [self.view addSubview:button1];
    
    
    
    //接收通知
    [[NSNotificationCenter defaultCenter]addObserver:self selector:@selector(notifictionBack) name:MPMoviePlayerPlaybackDidFinishNotification object:nil];
    
    
}

- (void)btnClicked{
    
    CustomViewController * vc =[[CustomViewController alloc]initWithContentURL:[NSURL URLWithString:@"http://localhost/share/1.mp4"]];
    [vc.moviePlayer prepareToPlay];
    [vc.moviePlayer play];
    
    [self presentViewController:vc animated:YES completion:nil];
    
    
}

- (void)notifictionBack
{
   //接收到播放完成的按钮
    NSLog(@"播放完成");
}

- (void)buttonClicked
{
      //MPMoviePlayerController这个是错误的
    MPMoviePlayerViewController * vc =[[MPMoviePlayerViewController alloc]initWithContentURL:[NSURL URLWithString:@"http://localhost/share/1.mp4"]];
    
    //进行缓冲播放
    [vc.moviePlayer prepareToPlay];
    //播放
    [vc.moviePlayer play];
    
    //把这个界面推出
    //[self presentViewController:vc animated:YES completion:nil];
    
    //如果是半屏，设置View
    vc.view.frame=CGRectMake(0, 0, self.view.frame.size.width, self.view.frame.size.height/2);
    [self.view addSubview:vc.view];
    
}
- (void)didReceiveMemoryWarning {
    [super didReceiveMemoryWarning];
    // Dispose of any resources that can be recreated.
}

/*
#pragma mark - Navigation

// In a storyboard-based application, you will often want to do a little preparation before navigation
- (void)prepareForSegue:(UIStoryboardSegue *)segue sender:(id)sender {
    // Get the new view controller using [segue destinationViewController].
    // Pass the selected object to the new view controller.
}
*/

@end
