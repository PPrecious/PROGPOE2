# PROGPOE2
Submit Claims:
<Window x:Class="ProgPOE.SubmitClaim" 
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" 
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008" 
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:ProgPOE" 
        mc:Ignorable="d" 
        Title="SubmitClaim" Height="450" Width="800"> 
    <Grid Margin="10"> 
        <StackPanel> 
            <TextBlock Text="Submit Claim" FontSize="24" FontWeight="Bold" Margin="0,0,0,20" HorizontalAlignment="Center"/> 
            <StackPanel Orientation="Horizontal" Margin="0,0,0,10"> 
                <TextBlock Text="Hours Worked:" Width="120"/> 
                <TextBox x:Name="HoursWorkedTextBox" Width="120"/> 
            </StackPanel> 

            <StackPanel Orientation="Horizontal" Margin="0,0,0,10"> 
                <TextBlock Text="Hourly Rate:" Width="120"/> 
                <TextBox x:Name="HourlyRateTextBox" Width="120" IsReadOnly="True" Text="50"/> 
            </StackPanel> 

            <StackPanel Orientation="Horizontal" Margin="0,0,0,10"> 
                <TextBlock Text="Notes:" Width="120"/> 
                <TextBox x:Name="NotesTextBox" Width="350" Height="50" AcceptsReturn="True"/> 
            </StackPanel> 

            <StackPanel Orientation="Horizontal" Margin="0,0,0,10"> 
                <TextBlock Text="Supporting Documents:" Width="120"/> 
                <Button Content="Browse..." Width="120" Click="BrowseFiles_Click"/> 
            </StackPanel> 

            <ListBox x:Name="UploadedFilesListBox" Height="100" Margin="0,10,0,0"/> 
            <Button Content="Submit Claim" Width="120" HorizontalAlignment="Center" Margin="0,20,0,0" Click="SubmitClaimButton_Click"/> 
            <TextBlock Text="Claim Status" FontSize="18" FontWeight="Bold" Margin="0,30,0,5"/> 
            <DataGrid x:Name="ClaimStatusDataGrid" AutoGenerateColumns="False" Height="200" Margin="0,10,0,0"> 

                <DataGrid.Columns> 
                    <DataGridTextColumn Header="Lecturer ID" Binding="{Binding LecturerId}" Width="100"/> 
                    <DataGridTextColumn Header="Hours Worked" Binding="{Binding HoursWorked}" Width="100"/> 
                    <DataGridTextColumn Header="Amount Due" Binding="{Binding AmountDue}" Width="100"/> 
                    <DataGridTextColumn Header="Status" Binding="{Binding Status}" Width="100"/> 
                </DataGrid.Columns> 
            </DataGrid> 
        </StackPanel> 
    </Grid> 
</Window> 

Approve claims:
<Window x:Class="ProgPOE.ApproveClaims" 
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" 
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" 
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008" 
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006" 
        xmlns:local="clr-namespace:ProgPOE" 
        mc:Ignorable="d" 
        Title="Approve Claims" Height="600" Width="800"> 

    <Grid Margin="10"> 
        <StackPanel> 
            <TextBlock Text="Pending Claims" FontSize="24" FontWeight="Bold" Margin="0,0,0,20" HorizontalAlignment="Center"/> 
            <StackPanel Orientation="Horizontal" HorizontalAlignment="Center" Margin="0,0,0,10"> 
                <Button Content="Show All" Width="100" Margin="5" Click="ShowAllClaims_Click"/> 
                <Button Content="Show Approved" Width="100" Margin="5" Click="ShowApprovedClaims_Click"/> 
                <Button Content="Show Rejected" Width="100" Margin="5" Click="ShowRejectedClaims_Click"/> 
            </StackPanel> 

            <DataGrid x:Name="ClaimsDataGrid" AutoGenerateColumns="False" Height="400" Margin="0,10,0,0" IsReadOnly="True" SelectionMode="Single"> 
                <DataGrid.Columns> 
                    <DataGridTextColumn Header="Lecturer ID" Binding="{Binding LecturerId}" Width="100"/> 
                    <DataGridTextColumn Header="Hours Worked" Binding="{Binding HoursWorked}" Width="100"/> 
                    <DataGridTextColumn Header="Amount Due" Binding="{Binding AmountDue, StringFormat=C}" Width="100"/> 
                    <DataGridTextColumn Header="Status" Binding="{Binding Status}" Width="100"/> 
                    <DataGridTemplateColumn Header="Actions" Width="200"> 
                        <DataGridTemplateColumn.CellTemplate> 
                            <DataTemplate> 
                                <StackPanel Orientation="Horizontal"> 
                                    <Button Content="Approve" Margin="5" Click="ApproveButton_Click"/> 
                                    <Button Content="Reject" Margin="5" Click="RejectButton_Click"/> 
                                </StackPanel> 
                            </DataTemplate> 
                        </DataGridTemplateColumn.CellTemplate> 
                    </DataGridTemplateColumn> 
                </DataGrid.Columns> 
            </DataGrid> 
        </StackPanel> 
    </Grid> 
</Window> 

Upoload document:
<Window x:Class="ProgPOE.UploadDocuments" 
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" 
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" 
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008" 
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006" 
        xmlns:local="clr-namespace:ProgPOE" 
        mc:Ignorable="d" 
        Title="UploadDocuments" Height="450" Width="800"> 
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
