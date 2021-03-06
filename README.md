# TL;DR
Add the nuget package https://www.nuget.org/packages/Vapolia.XamarinFormsGesture/
to ALL your Xamarin Forms projects (ios, android, shared/pcl).

In your Android/ios projects, before initializing xamarin forms, call PlatformGestureEffect.Init() to force the discovery of the gestures by the Xamarin Forms plugin engine.

# XamarinFormsGesture
Xamarin Form Gesture Effects  
Supports iOS and Android.

Add "advanced" gestures to Xamarin Forms. Available on all views. Sample use:

    <Label Text="Click here" Style="{StaticResource LinkLabel}" ui:Gesture.TapCommand="{Binding OpenLinkCommand}" />

# Quick start

Add Gesture.TapCommand on any xaml view:

    <Label Text="Click here" Style="{StaticResource LinkLabel}" ui:Gesture.TapCommand="{Binding OpenLinkCommand}" />

Declare the corresponding namespace:

    <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             ...
             xmlns:ui="clr-namespace:Vapolia.Lib.Ui;assembly=XamarinFormsGesture"
    >

And in the viewmodel:
        
    public Command OpenLinkCommand => new Command(() =>
    {
        //do something
    });

# Doc

Supported Gestures:

    TapCommand (ICommand)
    TapCommand2 (Command<Point>) where point is the tap position in the view
    SwipeLeftCommand
    SwipeRightCommand
    SwipeTopCommand
    SwipeBottomCommand
    PanCommand (Command<Point>) where point is the translation in the view from the start point of the pan gesture

Only commands are supported (PR welcome for events). No .NET events. 
So you must use the MVVM pattern (https://developer.xamarin.com/guides/xamarin-forms/xaml/xaml-basics/data_bindings_to_mvvm/).
