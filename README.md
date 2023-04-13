<!-- default badges list -->
<!-- default badges end -->
# DataGrid for .NET MAUI - Infinite Scrolling

This example demonstrates how to implement infinite scrolling in [Data Grid](https://docs.devexpress.com/MAUI/403255/data-grid/data-grid).

<img width="30%" src="https://user-images.githubusercontent.com/12169834/230103799-e52c384f-3efe-4428-b663-35756da1fe59.png"/>

## Implementation Details

* Set the [IsLoadMoreEnabled](https://docs.devexpress.com/MAUI/DevExpress.Maui.DataGrid.DataGridView.IsLoadMoreEnabled) property to `true` to enable infinite scrolling in Data Grid.
* Bind the [DataGridView.LoadMoreCommand](https://docs.devexpress.com/MAUI/DevExpress.Maui.DataGrid.DataGridView.LoadMoreCommand) property to a view model's command that loads new items in the command's Execute method. Data Grid automatically invokes this command when a user scrolls to the end.
* Set the [LoadMoreCommand](https://docs.devexpress.com/MAUI/DevExpress.Maui.DataGrid.DataGridView.LoadMoreCommand)'s **CanExecute** property to `false` to disable infinite when the scroll position reaches the last record in Data Grid.
* You can set the [IsRefreshing](https://docs.devexpress.com/MAUI/DevExpress.Maui.DataGrid.DataGridView.IsRefreshing) property to `true` to display a wait indicator while Data Grid is loading a new portion of data. Once the load operation is complete, set [IsRefreshing](https://docs.devexpress.com/MAUI/DevExpress.Maui.DataGrid.DataGridView.IsRefreshing) to `false` to update displayed data.
* To load only the next portion of data, you can store a number of displayed rows and pass it to the [Skip](https://learn.microsoft.com/en-us/dotnet/api/system.linq.enumerable.skip) method. Then, pass the number of rows you want to display in DataGrid to the [Take](https://learn.microsoft.com/en-us/dotnet/api/system.linq.enumerable.take) method.
    ```
    allBlogs.Skip(startIndex).Take(batchSize);
    ```

    File to look at: [MainViewModel.cs](CS/MainViewModel.cs)

* Call [Browser.OpenAsync](https://learn.microsoft.com/en-us/dotnet/maui/platform-integration/appmodel/open-browser?view=net-maui-7.0&tabs=android#open-the-browser) and [Share.RequestAsync](https://learn.microsoft.com/en-us/dotnet/maui/platform-integration/data/share?view=net-maui-7.0&tabs=android#share-text-and-links) methods to open a blog post in a browser and display the native share dialog.


## Files to Look At

* [MainPage.xaml](CS/MainPage.xaml)
* [MainPage.xaml.cs](CS/MainPage.xaml.cs)
* [MainViewModel.cs](CS/MainViewModel.cs)
* [Styles.xaml](CS/Resources/Styles/Styles.xaml)

## Documentation

* [Featured Scenario: Infinite Scrolling](https://docs.devexpress.com/MAUI/404358)
* [Featured Scenarios](https://docs.devexpress.com/MAUI/404291)
* [Load More in .NET MAUI Data Grid](https://docs.devexpress.com/MAUI/403264/data-grid/load-more)

## More Examples

* [DevExpress Data Grid for .NET MAUI](https://github.com/DevExpress-Examples/maui-data-grid/)
* [DevExpress Mobile UI for .NET MAUI](https://github.com/DevExpress-Examples/maui-demo-app/)
