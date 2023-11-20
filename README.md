# How-to-customize-the-color-based-on-the-y-value-in-Blazor-chart

This article explains how to set different color to its segment based on its Y value in the [Blazor chart](https://www.syncfusion.com/blazor-components/blazor-charts).

**Customizing point color based on Y value using OnPointRender event**

This can be achieved by using [OnPointRender](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartEvents.html#Syncfusion_Blazor_Charts_ChartEvents_OnPointRender) event. This event triggers before each point for the series is rendered.

The following properties are available in the [PointRenderEventArgs](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.PointRenderEventArgs.html).

•	[Border](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.PointRenderEventArgs.html#Syncfusion_Blazor_Charts_PointRenderEventArgs_Border) – Specifies the color and the width of the point border.

•	[Fill](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.PointRenderEventArgs.html#Syncfusion_Blazor_Charts_PointRenderEventArgs_Fill) – Specifies the fill color of the point.

•	[Height](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.PointRenderEventArgs.html#Syncfusion_Blazor_Charts_PointRenderEventArgs_Height) – Specifies the current point’s height.

•	[Shape](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.PointRenderEventArgs.html#Syncfusion_Blazor_Charts_PointRenderEventArgs_Shape) – Specifies the marker shape of the point.

•	[Width](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.PointRenderEventArgs.html#Syncfusion_Blazor_Charts_PointRenderEventArgs_Width) – Specifies the current point’s width.

We can customize the Segment color based on Y value by specifying the Fill property of the [PointRenderEventArgs](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.PointRenderEventArgs.html).

The following code example illustrates this.

**C#**
    
```cshtml

@using Syncfusion.Blazor.Charts

<SfChart>     
    <ChartEvents OnPointRender="PointRender"></ChartEvents>
    <ChartSeriesCollection>
        <ChartSeries DataSource="@Data" XName="XValue" YName="YValue" Type="ChartSeriesType.Column" />
    </ChartSeriesCollection>
</SfChart>

@code {
    public class ChartData
    {
        public double XValue { get; set; }
        public double YValue { get; set; }
    }
    public List<ChartData> Data = new List<ChartData>
    {
        new ChartData { XValue = 10, YValue = 10 },
        new ChartData { XValue = 20, YValue = 25 },
        new ChartData { XValue = 30, YValue = 30 },
        new ChartData { XValue = 40, YValue = 10 },
        new ChartData { XValue = 50, YValue = 30 },
        new ChartData { XValue = 60, YValue = 25 },
        new ChartData { XValue = 70, YValue = 50 },
    };
    public void PointRender(PointRenderEventArgs args)
    {
        if(args.Point.YValue <= 20)
        {
            args.Fill = "red";
        }
        if (args.Point.YValue > 20 && args.Point.YValue <= 40)
        {
            args.Fill = "blue";
        }
        if(args.Point.YValue > 40)
        {
            args.Fill = "green";
        }
    }
}

```

The following screenshot illustrate the output of the above code snippet.

**Output:**

![](/Segment-Color-customization-based-on-Y-Value.png)

**Conclusion**

I hope you enjoyed learning how to customize the segment color based on Y value of Blazor Chart Component.

You can refer to our [Blazor Chart feature tour](https://www.syncfusion.com/blazor-components/blazor-charts) page to know about its other groundbreaking feature representations and [documentation](https://blazor.syncfusion.com/documentation/chart/getting-started), and how to quickly get started for configuration specifications. You can also explore our [Blazor Chart example](https://blazor.syncfusion.com/demos/chart/line?theme=bootstrap5) to understand how to create and manipulate data.

For current customers, you can check out our components from the [License and Downloads](https://www.syncfusion.com/sales/teamlicense) page. If you are new to Syncfusion, you can try our 30-day [free trial](https://www.syncfusion.com/downloads/blazor) to check out our other controls.

If you have any queries or require clarifications, please let us know in the comments section below. You can also contact us through our [support forums](https://www.syncfusion.com/forums), [support portal](https://support.syncfusion.com/create), or [feedback portal](https://www.syncfusion.com/feedback/blazor-components?control=charts). We are always happy to assist you!