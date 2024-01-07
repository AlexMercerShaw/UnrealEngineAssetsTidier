# UnrealEngineAssetsTidier
Documentation
  ![Image text](https://raw.github.com/AlexMercerShaw/UnrealEngineAssetsTidier/main/Untitled-1.png)
  
Explanation:
This code appears to be the implementation of a utility class for organizing game assets. It includes functions for finding referenced asset paths and creating folders based on asset types. Here is a breakdown of each function:

GetAllReferencePathRecursive function: Recursively retrieves the paths of all dependent assets for the selected asset and stores them in the ReferencedAssetPaths array.

GetAllReferencePath function: Calls the GetAllReferencePathRecursive function to retrieve the paths of all dependent assets for the selected asset.

CreateFolderByType function: Creates subfolders within a specified folder based on the asset type and moves the assets to their corresponding folders. It also records the new paths for each asset.

CreateFolder function: Creates a folder at a specified path.


Usage Documentation:
1. Include the AssetsTidyToolsBPLibrary.h header file:
#include "AssetsTidyToolsBPLibrary.h"
2. Call the function to get referenced asset paths:
FString SelectedAssetPath = "/Game/Path/To/Your/Selected/Asset";
TArray<FString> ReferencePath;
UAssetsTidyToolsBPLibrary::GetAllReferencePath(SelectedAssetPath, ReferencePath);
// The ReferencePath array will now contain the paths of all dependent assets
3. Call the function to create folders based on asset types:
FString MainFolderName = "MainFolder";
TArray<FString> ReferencePath;
// Get the ReferencePath array here (omitted for brevity)
TArray<FString> NewPath;
UAssetsTidyToolsBPLibrary::CreateFolderByType(MainFolderName, ReferencePath, NewPath);
// The NewPath array will now contain the new paths of all assets after moving them to the corresponding folders
4. Create a folder:
FString Path = "Your/Desired/Path";
UAssetsTidyToolsBPLibrary::CreateFolder(Path);
// If the specified path does not exist, it will be created
These explanations and examples should help developers understand the functionality of the code and correctly utilize the functions within it. If you have any further questions or need additional assistance, please feel free to let me know.


---------------------------------------------------------------------------------------------------


How to use the plug-in:
Make sure the project is backed up before use

1. Select the asset recommendation level to be sorted individually, then enter the name of the folder to be sorted, and click Organize. After the execution is completed, remember to save all and perform repair redirection. see Releases 1.gif

2. Select multiple files to be sorted and enter the current corresponding name and click Organize. A folder with the entered name will be created in the current directory. see Releases 2.gif

3. After clicking, it will be renamed according to the Class type. The renaming rules are on the Switch node of the blueprint.see Releases 3.gif



