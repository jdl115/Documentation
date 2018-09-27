# Synchronization

After [AdSpots](xref:unity-adspot-term) and [Trivver settings](xref:unity-settings-term) are set up properly you have to make Synchronization. This process will collect data about all spots in your project validate it \(check if there are any spots without categories and all guid's are unique\) and send to the server. After this process you can see all your spots in the Developer Dashboard.

> \[!NOTE\] You have to make synchronization each time you:
>
> * Add new/delete AdSpots.
> * Modifying categories or description of existing AdSpots.
> * Changing scenes names or moving scenes to another folder.

Synchronization window can be accessed via Trivver menu or in the Trivver Settings by pressing Sync data button.

![Sync data window](.gitbook/assets/sync_data-window.png)

> \[!NOTE\] To be able to make synchronization, you have to be logged in in Trivver Settings.

In this window you can see a list of scenes of your project. You can choose to show only scenes from build settings or from overall project. Near each scene there is a checkbox that allows to exclude/include scenes from synchronization.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Property</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Current version</td>
      <td style="text-align:left">Current game version. Synchronization will be associated with this version.
        This parameter is set from Trivver Settings. For more info see <a href="xref:unity-versions-term">Versions and publishing section</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Sync images</td>
      <td style="text-align:left">If true AdSpot previews will be uploaded to the server. If you changed
        AdSpots and didn't change previews you can uncheck this toggle to save
        sync time.</td>
    </tr>
    <tr>
      <td style="text-align:left">Project scenes</td>
      <td style="text-align:left">
        <p>Project - scene list will show all scenes from the project.</p>
        <p>Build settings - scene list will show only scenes from build settings.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Sync</td>
      <td style="text-align:left">Start synchronization.</td>
    </tr>
  </tbody>
</table>While the synchronization Trivver opens all specified scenes and collects all adSpots data and then sends it to the server. So, before you start the process, make sure that you saved all changes in currently opened scene.

