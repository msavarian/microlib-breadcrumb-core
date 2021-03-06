Microlib.BreadCrumb.Core
=======

<p align="left">
  <a href="https://github.com/msavarian/DNTBreadCrumb.Core">
     <img alt="GitHub Actions status" src="https://github.com/msavarian/DNTBreadCrumb.Core/workflows/.NET%20Core%20Build/badge.svg">
  </a>
</p>


> This is a fork from [DNTBreadCrumb.Core](https://github.com/VahidN/DNTBreadCrumb.Core) 
> I tried to add a new property for adding css class to the bredcrumb.
```
asp-bootstrap-extra-css-classes="ExtraClass1 ExtraClass2"
```

`Microlib.BreadCrumb.Core` Creates custom breadcrumbs, based on Twitter Bootstrap 3.x and 4.x features for ASP.NET Core applications.



Install via NuGet
-----------------
To install Microlib.BreadCrumb.Core, run the following command in the Package Manager Console:

```
PM> Install-Package Microlib.BreadCrumb.Core
```

You can also view the [package page](http://www.nuget.org/packages/Microlib.BreadCrumb.Core/) on NuGet.



Usage:
-----------------
- After installing the Microlib.BreadCrumb.Core package, add the following definition to the [_ViewImports.cshtml](/src/DNTBreadCrumb.Core.TestWebApp/Views/_ViewImports.cshtml) file:
```csharp
@addTagHelper *, DNTBreadCrumb.Core
```

- Then modify the [_Layout.cshtml](/src/DNTBreadCrumb.Core.TestWebApp/Views/Shared/_Layout.cshtml) file to add its new tag-helper:
```xml
 <breadcrumb asp-homepage-title="Home"
             asp-homepage-url="@Url.Action("Index", "Home", values: new { area = "" })"
             asp-bootstrap-version="V3"
             asp-bootstrap-extra-css-classes="ExtraClass1 ExtraClass2"
             asp-homepage-glyphicon="glyphicon glyphicon-home"></breadcrumb>
```


- Now you can add the `BreadCrumb` attributes to your controller or action methods:
```csharp
[BreadCrumb(Title = "Home", UseDefaultRouteUrl = true, Order = 0)]
public class HomeController : Controller
{
   [BreadCrumb(Title = "Main index", Order = 1)]
   public ActionResult Index()
   {
      return View();
   }
```
Please follow the [TestWebApp](/src/DNTBreadCrumb.Core.TestWebApp), [TestWebApp.WithFeatureFolders](/src/DNTBreadCrumb.Core.TestWebApp.WithFeatureFolders) and [TestWebApp.WithRazorPages](/src/DNTBreadCrumb.Core.TestWebApp.WithRazorPages) samples for more scenarios.
