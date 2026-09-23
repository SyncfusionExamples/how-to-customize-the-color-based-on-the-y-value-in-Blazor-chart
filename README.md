# Customize Segment Colors Based on Y-Value in Syncfusion Blazor Chart

## Overview

This sample demonstrates how to customize segment colors in a Syncfusion [Blazor Charts](https://www.syncfusion.com/blazor-components/blazor-charts) according to the Y-value of each data point. The chart renders a column series and uses the `OnPointRender` event to evaluate every point before it is displayed. Based on predefined Y-value thresholds, the sample dynamically assigns different colors to chart segments, making it easier to visually identify low, medium, and high-value data points. This approach is useful for dashboards, KPI monitoring, threshold analysis, and data visualization scenarios where conditional formatting improves readability and decision-making.

## Key Features

- Uses the `SfChart` component to render chart data.
- Defines a `ChartSeries` with `Type="ChartSeriesType.Column"`.
- Binds data using the `DataSource` property.
- Maps chart axes through `XName="XValue"` and `YName="YValue"`.
- Handles the `OnPointRender` event using the `ChartEvents` component.
- Uses `PointRenderEventArgs.Fill` to customize point colors before rendering.
- Accesses point values through `args.Point.YValue`.
- Applies conditional color rules:
  - Red for values less than or equal to 20.
  - Blue for values greater than 20 and less than or equal to 40.
  - Green for values greater than 40.
- Demonstrates a strongly typed `ChartData` model with `XValue` and `YValue` properties.
- Shows how per-point styling can be implemented without modifying the underlying data source.

## Prerequisites

- [Visual Studio 2022](https://visualstudio.microsoft.com/vs/) or [Visual Studio Code](https://code.visualstudio.com/)
- [.NET SDK](https://dotnet.microsoft.com/en-us/download/dotnet) compatible with the project's target framework

## How to Run the Project

**Visual Studio 2022**

1. Clone or download this repository.
2. Open the project file:

   `SegmentColor.csproj`

3. Restore NuGet packages.
4. Build the project.
5. Run the application using `Ctrl+F5`.

**Visual Studio Code**

1. Clone or download this repository.
2. Open the repository folder in Visual Studio Code.
3. Open the integrated terminal.
4. Navigate to the project directory.

```bash
cd SizeOfPieOrDoughnutChart
```

5. Restore NuGet packages:

```bash
dotnet restore
```

6. Run the application:

```bash
dotnet run
```

7. Open the local URL displayed in the console output.

## Project Structure

`SegmentColor/Pages/Index.razor` - Contains the Syncfusion chart, sample data source, column series definition, and `OnPointRender` implementation used to apply colors according to Y-values.

## Support and Feedback

- For general product questions, visit the [Syncfusion Community Forum](https://www.syncfusion.com/forums) or [Syncfusion Support](https://www.syncfusion.com/support).
- To report an issue specific to this sample, open a GitHub issue in this repository.
- Refer to the official Syncfusion documentation for chart rendering and point customization: https://help.syncfusion.com/chart-sdk/blazor/charts/getting-started

## License

This is a Syncfusion sample project provided to demonstrate product usage. Review the [Syncfusion license terms](https://www.syncfusion.com/sales/pricing?category=ui-components) before using Syncfusion components in your own applications.