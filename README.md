# PROGPOE2
Submit Claims:
<Window x:Class="WpfApp2.submitClaims"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:WpfApp2"
        mc:Ignorable="d"
        Title="submitClaims" Height="450" Width="800">
    <Grid Margin="10">
        <StackPanel>
            <TextBlock Text="Submit Claim" FontSize="24" FontWeight="Bold" HorizontalAlignment="Center"/>
            <StackPanel Orientation="Horizontal" Margin="0,0,0,10">
                <TextBlock Text="Lecturer ID:" Width="120"/>
                <TextBox x:Name="LecturerIdTextBox" Width="120"/>
            </StackPanel>
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
            <Button Content="Submit Claim" Width="120" HorizontalAlignment="Center" Click="SubmitClaimButton_Click"/>
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
<Window x:Class="WpfApp2.claimsApproved"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:WpfApp2"
        mc:Ignorable="d"
        Title="claimsApproved" Height="450" Width="800">
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
<Window x:Class="WpfApp2.uploadDocuments"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:WpfApp2"
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


