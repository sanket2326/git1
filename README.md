GABUILD VERIFICATION TOOL 

 

About Tool:  GABUILD Verification Tool is internal tool that will help us to verify if any deliverables files are missing our unpackaged wrongly in the new Version of PCOMM. 

                           Also, instead of doing the build verification manually, User can run this tool to generate the reports which will indicate whether the DLL or EXE file is packaged correctly  

                           along with the Version information. 

Features:  

Network Location: PCOMM build can be copied from network location 

Command Line arguments: User can also run this tool using the Command line by providing the required parameter. 

Batch Execution: User can run this tool using the .Bat file where multiple Version of PCOMM build can be verified in single execution 

Build Comparison: Two and more PCOMM build can be verified by specifying the path of PCOMM Build 

CSV FILE Report: This tool will create the report indicating the status of each DLL and .EXE file in CSV file 

Validity Check: Report will highlight whether any DLL or .exe is missing or packaged wrongly at different Location, if everything is fine it will show “PASS” or “FAIL.” 

 

HOW TO RUN THE TOOL 

 

The tool can be run using the .bat file where multiple Version of PCOMM build can be verified in single execution, however user needs to provide the specific parameter. 

Below is the syntax of command with parameter to run the tool. 

 

Case 1: Use the tool to create the Template file for PCOMM build 

Syntax: [Path of tool] [Path of PCOMM build] [Version] [NULL] [Path of Report file] 

Example: GABuildVerificationTool.exe “D:\Testing\pcommv14.0.0\mmls0507\mls” 14000  "  "  "D:\Testing\pcommv14.0.0\1400.csv" 

Note:  

[Path of PCOMM build]: Always Provide the path of PCOMM build till “mls\cht\chs\kor” folder (For example: “pcommv14.0.0\mmls0507\mls") 

[Version]:  Version of PCOMM Build (For example: 14000, 14020, 13030, 12050 ,12060) 

[NULL]: While Creating the Template file, keep this as NULL. 

[Path of Report file]: Provide the path of template.CSV file (For example: "D:\Testing\140200.csv"). This parameter is optional. If no path is specified, then default path [Path of PCOMM build] will be taken. 

 

Screenshot: Below command is used to create the Template file for specific PCOMM build (Example PCOMM 14000), However user can provide the path location of their own choice. 

 

After executing the above command console will display the below output.Output: 

  

  

Here console Displayed as “Failed “which is expected while creating the Template file because it is the original file which will be used to compared with other build of PCOMM. 

Output will show the number for DLL/EXE file which matched the specified Version. 

Match count =499 Means, there are total 499 DLL/EXE file which matched the version 14000.  

Unmatched Count= 159 indicates the number of DLL/EXE other than 14000 version.  

Note: The Template.CSV file will be created at the specified Location [Path of Report file].  

(In Above image the Template file is "D:\Testing\pcommv14.0.0\1400.csv) 

 

Below is the screenshot of Template.CSV(1400.csv) file generated. 

 

First column is EXE/DLL file name present under the GA build. 

Second column is Build Version which indicated the version of the file 

Third column is Build Date which indicates the Last Modified date of the file. 

Fourth column is Path of corresponding DLL/EXE file under the GA BUILD. 

Fifth column is Verification which is “Not compared” since this is the Template file. 

 

Case 2: Use the tool to create the Report after the GA BUILD Comparison 

Syntax: [Path of tool] [Path of PCOMM build] [Version] [Path of Template file] [Path of Report file]  

Example: GABuildVerificationTool.exe  "D:\Testing\pcommv14.0.1\mmls1115\mls"  14010   "D:\Testing\pcommv14.0.0\1400.csv"   "D:\Testing\1401.csv" 

Note:  

[Path of PCOMM build]: Always Provide the path of PCOMM build till “mls\cht\chs\kor” folder (For example: “pcommv14.0.2\mmls0820\mls") 

[Version]:  Version of PCOMM Build (For example: 14000, 14020, 13030, 12050 ,12060) 

[Path of Template file]: Path of Template .CSV file created in Case 1([Path of Report file]) 

[Path of Report file]: Provide the path of template.CSV file (For example: "D:\Testing\140200.csv"). This parameter is optional. If no path is specified, then default path [Path of PCOMM build] will be taken. 

Screenshot: Below command is used to create the Template file for specific PCOMM build (Example PCOMM 14000), However user can provide the path location of their own choice. 

 

After executing the above command console will display the below output. 

Output: 

 

Here console Displayed “PASS “which indicates that Each DLL/file of the PCOMM build matches the Template file. It means that no DLL/EXE file is missing from the build. 

Note: If any of the file does not matched or any file is missing it will show the status as “FAILED” 

Output will show the number for DLL/EXE file which matched the specified Version. 

Match count =499 Means, there are total 499 DLL/EXE file which matched the version 14000.  

Unmatched Count= 159 indicates the number of DLL/EXE other than 14000 version.  

Note: The Report file of the comparison will be created at the specified Location [Path of Report file].  

(In Above image the report file is "D:\Testing\pcommv14.0.1\14010.csv) 

 

Below is the screenshot of Report.CSV(14010.csv) file generated. 

 

Note:  

First column is EXE/DLL file name present under the GA build. 

Second column is Build Version which indicated the version of the file 

Third column is Build Date which indicates the Last Modified date of the file. 

Fourth column is Path of corresponding DLL/EXE file under the GA BUILD. 

Fifth column is Verification which is “PASS/FAILED”. It shows pass if the corresponding DLL/EXE file matched otherwise it will shows as failed. 

 

BATCH FILE EXECUTION:  

User can run this tool using the .Bat file where multiple Version of PCOMM build can be verified in single execution 

Batch Script: 

Graphical user interface, application

Description automatically generated 

Edit the Below Parameter in the Batch File as per the Requirement 

TempSource: Path of PCOMM build which will be used as a template (It can be network path also) 

TemplateVersion: Version of the PCOMM build 

TempDestination: Local Path of PCOM build (Template Build) 

TempalateCSVPath: Path where the log file for Template build is Generated. 

Language: Language pack for PCOMM build (Example: mls, cht,chs,kor) 

 

ReportSource: Path of actual PCOMM build which will be used to compare with Template build (It can be network path also) 

ReportVersion: Version of Actual PCOMM build 

ReportDestination: Local path for Actual PCOMM build 

ReportCSVPath: Path where the log file for Actual PCOMM build is Generated. 

 

Note:   

TempSource, ReportSource, Always Provide the Path of PCOMM build till unzipped mmls/cht/chs/kor folder. 

Always keep the GABuildVerificationTool.exe file and GABuildVerificationTool.bat in same folder. 

 

Running the GABuildVerificationTool.bat: 

 

      To Run tool using the batch file, follow the below steps. 

Go to the location where GABuildVerificationTool.bat and GABuildVerificationTool.exe file is present.  

Edit the GABuildVerificationTool.bat file and provide the required parameter  

Launch the command prompt from the same location and run GABuildVerificationTool.bat 

 

Below Screenshot indicates how to run the tool using Batch file. 

Text

Description automatically generated 

 

After executing the above command console will display the below output. 

Output: 

  

A screenshot of a computer

Description automatically generated with medium confidence 

 

The command window will display the final output whether the Build comparison is Pass or Fail. 

Also, in case of pass and failure, we can compare the below excel file generated for Template build as well as PCOMM build. 

For example: 

TempalateCSVPath =   "D:\Testing\13020.csv"(Path as per given in batch file) 

ReportCSVPath =         "D:\Testing\13030.csv"(Path as per given in batch file) 

 

We can compare the above excel file to get more information about the pass or failure status of the PCOMM build. 

 

LIMITATION:  

MSI File Verification: The tool is not applicable to verify the .msi file 

Unzipped PCOMM build from network Location 

 
