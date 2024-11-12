# Maui App Navigation Notes

This README provides useful examples for page navigation in .NET MAUI applications, including techniques like using `NavigationPage`, `InsertPageBefore`, `PopToRootAsync`, and other navigation methods.

## Table of Contents
- [Setting Up Navigation](#setting-up-navigation)
- [Replacing a Page with `PopToRootAsync`](#replacing-a-page-with-poptorootasync)
- [Navigating with Push and Pop](#navigating-with-push-and-pop)
- [Other Useful Navigation Techniques](#other-useful-navigation-techniques)

---

### Setting Up Navigation

In MAUI, to manage navigation effectively, ensure that your main page is a `NavigationPage`. This will allow access to the full range of navigation features.

`MainPage = new NavigationPage(new MainAppPage());`

### Replacing a Page with `PopToRootAsync`

To replace the current page after login with another page, use `InsertPageBefore` to add a new page and `PopToRootAsync` to reset the navigation stack.

`var mainAppPage = new NewPage1();`

`Navigation.InsertPageBefore(mainAppPage, this);`

`await Navigation.PopToRootAsync();`

### Navigating with Push and Pop

Instead of `PopToRootAsync`, you can use `PushAsync` to add a new page on top of the current page and use `PopAsync` to return to the previous page, maintaining the current navigation stack.

`await Navigation.PushAsync(new NextPage());`

`await Navigation.PopAsync();`
