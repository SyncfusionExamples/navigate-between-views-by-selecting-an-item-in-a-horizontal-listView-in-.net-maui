# How to navigate across views by selecting an item from the horizontal ListView (SfListView) in .NET MAUI?

The [.NET MAUI ListView](https://www.syncfusion.com/maui-controls/maui-listview) allows you to layout items horizontally by setting the [Orientation](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.ListView.SfListView.html#Syncfusion_Maui_ListView_SfListView_Orientation) property to `Horizontal`. You can navigate or switch views by handling the [ItemTapped](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.ListView.SfListView.html#Syncfusion_Maui_ListView_SfListView_ItemTapped) event to bring a selected view to the foreground.

**XAML**
```
<ContentPage.Content>
    <Grid>
        <Grid.RowDefinitions>
            <RowDefinition Height="50"/>
            <RowDefinition Height="*"/>
            <RowDefinition Height="100"/>
        </Grid.RowDefinitions>
        <Label Text="Tap image to expand" BackgroundColor="#d3d3d3" FontSize="Medium" FontAttributes="Bold" VerticalTextAlignment="Center"/>
        <Grid BackgroundColor="Bisque" Grid.Row="1" x:Name="GridView" Padding="0,20,0,0">
            <Grid.RowDefinitions>
                <RowDefinition Height="60" />
                <RowDefinition Height="50" />
                <RowDefinition Height="50" />
            </Grid.RowDefinitions>
            <Image Source="{Binding ContactImage}"  VerticalOptions="Center" HorizontalOptions="Center" HeightRequest="70" Grid.Row="0"/>
            <Label LineBreakMode="NoWrap" Padding="0,20,0,0" TextColor="#474747" Text="{Binding ContactName}" Grid.Row="1" FontSize="20" HorizontalTextAlignment="Center" />
            <Label Grid.Row="2" TextColor="#474747"  LineBreakMode="NoWrap"  Text="{Binding ContactNumber}" FontSize="20" HorizontalTextAlignment="Center" />
        </Grid>
        <listView:SfListView x:Name="list" Grid.Row="2" ItemTapped="list_ItemTapped" SelectionBackground="#d3d3d3" ItemSize="70" ItemsSource="{Binding Items}" ItemSpacing="0,0,5,0" SelectionMode="Single" Orientation="Horizontal">
            <listView:SfListView.ItemTemplate>
                <DataTemplate x:Name="ItemTemplate" >
                    <ViewCell>
                        <ViewCell.View>
                            <Grid x:Name="grid" RowSpacing="5">
                                <Image Source="{Binding ContactImage}"
                VerticalOptions="Center"
                HorizontalOptions="Center"
                HeightRequest="50">
                                </Image>
                            </Grid>
                        </ViewCell.View>
                    </ViewCell>
                </DataTemplate>
            </listView:SfListView.ItemTemplate>
        </listView:SfListView>
    </Grid>
</ContentPage.Content>
```

**C#**
```
public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();
    }

    private void list_ItemTapped(object sender, Syncfusion.Maui.ListView.ItemTappedEventArgs e)
    {
        GridView.BindingContext = e.DataItem;
    }
}
```


**Conclusion**

I hope you enjoyed learning how to navigate across views by selecting an item from the horizontal listview in .NET MAUI ListView.

You can refer to our [.NET MAUI ListView ](https://www.syncfusion.com/maui-controls/maui-listview) feature tour page to know about its other groundbreaking feature representations and [documentation](https://help.syncfusion.com/maui/listview/getting-started), and how to quickly get started with configuration specifications. Explore our [.NET MAUI ListView example](https://github.com/syncfusion/maui-demos/tree/master/MAUI/ListView) to understand how to create and manipulate data.

You can check out our components from the [License and Downloads](https://www.syncfusion.com/sales/teamlicense) page for current customers. If you are new to Syncfusion®, try our 30-day [free trial](https://www.syncfusion.com/downloads/maui/confirm) to check out our other controls.

Please let us know in the comments section if you have any queries or require clarification. You can also contact us through our [support forums](https://www.syncfusion.com/forums), [Direct-Trac](https://support.syncfusion.com/create), or [feedback portal](https://www.syncfusion.com/feedback/maui?control=sflistview). We are always happy to assist you!
