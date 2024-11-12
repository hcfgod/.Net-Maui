# .NET MAUI Navigation Guide

Welcome to your .NET MAUI app navigation guide! This guide covers various ways to handle page navigation, including replacing pages, pushing new pages, and managing navigation stacks. Let's dive in!

## Table of Contents
1. [Setting Up NavigationPage](#setting-up-navigationpage)
2. [Navigating Between Pages](#navigating-between-pages)
   - [Using InsertPageBefore and PopToRootAsync](#using-insertpagebefore-and-poptorootasync)
   - [Using PushAsync and PopAsync](#using-pushasync-and-popasync)
   - [Replacing Pages with PushAsync](#replacing-pages-with-pushasync)
3. [Additional Tips](#additional-tips)

## Setting Up NavigationPage

To enable navigation in your .NET MAUI app, start by ensuring your main page is wrapped in a `NavigationPage`. This setup allows you to use navigation methods like `PushAsync`, `PopAsync`, `PopToRootAsync`, and more.

In `App.xaml.cs`:

```csharp
public App()
{
    MainPage = new NavigationPage(new MainPage()); // Wrap MainPage in NavigationPage
}
