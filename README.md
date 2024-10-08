# Unused Asset Remover

**Unused Asset Remover** is a PowerShell script designed to clean up unused asset files (images, JavaScript, and CSS) from a project's public or asset directory. The script checks if these files are referenced in your view files (such as `.blade.php` files in Laravel) and removes any that are no longer in use. It is versatile and can be adapted for use with any project that uses static assets and HTML-based view templates.

## Features

- Scans for unused images, JavaScript, and CSS files in your public/asset folder.
- Supports exclusion of specific folders from the cleanup process (e.g., `storage`, `vendor`).
- Automatically deletes unreferenced files.
- Provides a summary of how many files were processed, deleted, and retained.
- Customizable for any web framework (not limited to Laravel).

## Requirements

- Windows PowerShell 5.1 or higher
- Delete Permission to the files

## Installation

1. Download or clone the repository:
    ```bash
    git clone https://github.com/tauseedzaman/Unused-Asset-Remover.git
    ```

2. Navigate to the project directory:
    ```bash
    cd Unused-Asset-Remover
    ```

3. Open the script in any text editor and adjust the paths for your project:
    ```powershell
    $publicFolder = "C:\path\to\your\project\public"
    $viewsFolder = "C:\path\to\your\project\views"
    ```

4. Update the list of folders to exclude if necessary:
    ```powershell
    $excludeFolders = @("storage", "tmp", "vendor")
    ```

## Usage

1. Open PowerShell with administrative privileges.
2. Run the script:
    ```powershell
    .\script.ps1
    ```
3. The script will:
    - Scan your public folder for asset files (images, JS, CSS).
    - Compare the assets with your view files to check if they are being used.
    - Delete any unreferenced files.
    - Display a summary of how many files were processed, deleted, and kept.

### Example Output:

```bash
Deleting C:\path\to\your\project\public\images\old-image.png (Not referenced in any view file)
Deleting C:\path\to\your\project\public\js\unused-script.js (Not referenced in any view file)
Cleanup completed.
Total files processed: 200
Total files deleted: 50
Total files referenced (kept): 150
