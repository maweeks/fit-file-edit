# fit-file-edit

Attempting to remove laps from a `.fit` file.

Using this SDK (FIT 21.171 SDK Release Date: May 6, 2025 used): <https://developer.garmin.com/fit/download/>

Helpful to check output: <https://gotoes.org/strava/fitfileviewer.php>

## Steps to remove lap(s)

1. Download `.fit` file from Strava
2. Convert to `.csv` using

    ```bash
    java -jar ./FitSDKRelease_21.171.00/java/FitCSVTool.jar ./files/start.fit
    ```

3. Duplicate file and commit (for safety to not lose workout)
4. Remove laps and events
   a. To remove 1 lap: remove 1 event, remove 1 lap, and update the next lap. See commit `4016937c2bba8a9f7446bf94b98c95316ce027f7` for an example of 2 laps removed.
5. Convert to `.fit` using:

    ```bash
    java -jar ./FitSDKRelease_21.171.00/java/FitCSVTool.jar ./files/zfixed.csv
    ```

6. Check before vs after output using <https://gotoes.org/strava/fitfileviewer.php>
7. Open web pages of old activity for compare later
8. Delete old activity on Strava
9. Upload new activity to website
10. Open new activity and compare with old activity
