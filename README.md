# Expo DocumentPicker: Inaccessible File URIs When Selecting Multiple Files

This repository demonstrates a bug in the Expo DocumentPicker API where file URIs returned when selecting multiple files are inaccessible using the Expo FileSystem API.  The bug and its solution are outlined below.

## Bug Description

When using `DocumentPicker.getDocumentAsync` to select multiple files, the returned `selectedFiles` array contains URIs that cannot be read using `FileSystem.readAsStringAsync` or similar methods.  This results in an error.

## Solution

The solution involves using the `uri` property directly to open the file using a platform-specific method (e.g., `Linking.openURL`). This circumvents the limitations of the Expo FileSystem API when dealing with multiple file selections.

## Usage

1. Clone this repository.
2. Run `npm install`.
3. Run the app in an Expo Go client or using the Expo CLI.