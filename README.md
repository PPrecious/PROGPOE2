# PROGPOE2
Submit Claims:
  Background="#F4F4F4">

    <Window.Resources>
        <Style TargetType="Button">
            <Setter Property="Margin" Value="5"/>
            <Setter Property="Padding" Value="10"/>
            <Setter Property="FontSize" Value="14"/>
            <Setter Property="Background" Value="#007ACC"/>
            <Setter Property="Foreground" Value="White"/>
            <Setter Property="BorderBrush" Value="Transparent"/>
            <Setter Property="Cursor" Value="Hand"/>
            <Setter Property="BorderThickness" Value="0"/>
            <Setter Property="FontWeight" Value="Bold"/>
            <Setter Property="Template">
                <Setter.Value>
                    <ControlTemplate TargetType="Button">
                        <Border Background="{TemplateBinding Background}" CornerRadius="5">
                            <ContentPresenter HorizontalAlignment="Center" VerticalAlignment="Center"/>
                        </Border>
                    </ControlTemplate>
                </Setter.Value>
            </Setter>
            <Style.Triggers>
                <Trigger Property="IsMouseOver" Value="True">
                    <Setter Property="Background" Value="#005DA3"/>
                </Trigger>
            </Style.Triggers>
        </Style>

        <Style TargetType="TextBlock">
            <Setter Property="Margin" Value="5"/>
            <Setter Property="FontFamily" Value="Segoe UI"/>
        </Style>
    </Window.Resources>

    <Grid>
        <DockPanel>
            <StackPanel DockPanel.Dock="Left" Width="250" Background="#EAEAEA" Padding="10">
                <TextBlock Text="Navigation" FontSize="20" FontWeight="Bold" Foreground="#333333"/>
                <Button Content="Submit Claim" Click="SubmitClaim_Click"/>
                <Button Content="Approve Claims" Click="ApproveClaims_Click"/>
                <Button Content="Upload Documents" Click="UploadDocuments_Click"/>
                <Button Content="Track Claim Status" Click="TrackStatus_Click"/>
            </StackPanel>

            <StackPanel Margin="10">
                <TextBlock Text="Welcome to the CMCS Dashboard" FontSize="26" FontWeight="Bold" Foreground="#007ACC"/>
                <TextBlock Text="Here you can manage your claims and documents." FontSize="16" Foreground="#555555"/>
                <TextBlock Text="Claim Status Overview" FontSize="20" FontWeight="SemiBold" Foreground="#333333"/>
                <TextBlock Text="No claims submitted yet." FontSize="14" Foreground="#777777" Margin="5"/>
            </StackPanel>
        </DockPanel>
    </Grid>
</Window>

Approve claims:
<Window x:Class="ProgPOE.claimsApproved"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:ProgPOE"
        mc:Ignorable="d"
        Title="Approve Claims" Height="600" Width="800">
    <Grid Margin="10">
        <StackPanel>
            <TextBlock Text="Claims Approved" FontSize="20" FontWeight="Bold" Margin="0,0,0,10"/>

            <DataGrid x:Name="ClaimsDataGrid" AutoGenerateColumns="False" Height="300" Margin="0,0,0,10" SelectionMode="Single">
                <DataGrid.Columns>
                    <DataGridTextColumn Header="Lecturer ID" Binding="{Binding LecturerId}" Width="*"/>
                    <DataGridTextColumn Header="Hours Worked" Binding="{Binding HoursWorked}" Width="*"/>
                    <DataGridTextColumn Header="Amount Due" Binding="{Binding AmountDue, StringFormat=C}" Width="*"/>
                    <DataGridTextColumn Header="Status" Binding="{Binding Status}" Width="*"/>
                </DataGrid.Columns>
            </DataGrid>

            <StackPanel Orientation="Horizontal" HorizontalAlignment="Center">
                <Button Content="Approve" Click="ApproveButton_Click" Width="100" Margin="5"/>
                <Button Content="Reject" Click="RejectButton_Click" Width="100" Margin="5"/>
            </StackPanel>

            <StackPanel Orientation="Horizontal" HorizontalAlignment="Center" Margin="0,10">
                <Button Content="Show All Claims" Click="ShowAllClaims_Click" Width="120" Margin="5"/>
                <Button Content="Show Approved Claims" Click="ShowApprovedClaims_Click" Width="150" Margin="5"/>
                <Button Content="Show Rejected Claims" Click="ShowRejectedClaims_Click" Width="150" Margin="5"/>
            </StackPanel>
        </StackPanel>
    </Grid>
</Window>

Upoload document:
<Window x:Class="ProgPOE.uploadDocuments"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:ProgPOE"
        mc:Ignorable="d"
        Title="uploadDocuments" Height="450" Width="800">
    <Grid Margin="10">

        <StackPanel>
            <TextBlock Text="Upload Supporting Documents" FontSize="20" FontWeight="Bold" Margin="0,0,0,10"/>
            <StackPanel Orientation="Horizontal" Margin="0,0,0,10">
                <TextBlock Text="Choose Files:" Width="120"/>
                <Button Content="Browse..." Width="120" Click="BrowseFiles_Click"/>
            </StackPanel>

            <ListBox Name="UploadedFilesListBox" Height="150" Margin="0,10,0,0"/>
            <Button Content="Upload" Width="120" HorizontalAlignment="Center" Click="UploadFiles_Click"/>
        </StackPanel>
    </Grid>
</Window> 

