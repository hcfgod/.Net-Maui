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

### Navigating with Push and Pop

Instead of using `PopToRootAsync`, you can navigate by pushing a new page onto the stack and later popping it to return to the previous page. This approach allows users to go back to the previous screen rather than resetting the stack.

- **Push a New Page**: Add a new page to the navigation stack.
  
  `await Navigation.PushAsync(new NextPage());`

- **Pop the Current Page**: Go back to the previous page on the stack.

  `await Navigation.PopAsync();`

### Other Useful Navigation Techniques

1. **Navigate Back to a Specific Page**: If you need to go back multiple pages to a specific one in the stack, use `PopToRootAsync` after inserting the target page before the current one.

   - Insert the page and reset to it:
   
     `Navigation.InsertPageBefore(targetPage, this);`
   
     `await Navigation.PopToRootAsync();`

2. **Remove a Page from the Stack**: To dynamically remove a page, simply navigate with `RemovePage`.

   - Remove a page from the stack:

     `Navigation.RemovePage(pageToRemove);`

3. **Modal Pages**: Use modal navigation to display pages that need to temporarily take over the screen, such as login screens or forms.

   - Display a modal page:

     `await Navigation.PushModalAsync(new ModalPage());`

   - Dismiss a modal page:

     `await Navigation.PopModalAsync();`
