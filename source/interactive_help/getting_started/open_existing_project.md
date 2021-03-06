# Open an existing project

The {{ProductName}} editor keeps track of the projects you create and work on. You can easily re-open any project when you launch the editor or by opening the **Project Manager** from the **File** menu.

You can also double-click a project file (`.stingray_project`) to open the project in the interactive editor, provided no other projects are open at the moment.

Sometimes, however, you may want to open an existing project that somebody else has created, but that doesn't yet show up in your **Project Manager** like a Revit Live scene or zipped interactive projects.

**To open an existing project for the first time:**

1.	Open the **Project Manager**. Do this either by launching the editor, or by selecting **File > Project Manager** from the main menu if you already have the editor running.

2.	Open the **My Projects** tab.

	![Add Existing](../images/project_manager_add_existing.png)

3.	Click **Add Existing**. In the dialog that appears, select the file type depending on the project you want to add and browse to the location of the project on your local computer. Select the *.stingray_project* or the *.zip* file for interactive projects and the *.lvsc* file for Live scenes and click **Open**.

	This adds the selected project to the *Projects* area of the **My Projects** tab.

	{{#if Stingray}}
	>	**Note:** If the project you want to open was created with a version of Stingray before 1.7, it might not have a *.stingray_project* file. If so, change the dialog's filter to look for `All Files (*.*)` instead of `Stingray Projects (*.stingray_project)`, and select your project's *settings.ini* file.
	{{/if}}

4.	(Optional) If your project was created using an earlier version of {{ProductName}}, do one of the following in the dialog box that appears:

	-	Click **Yes**.

		The editor migrates your resources and opens your project. After migration, you can no longer open your project with older versions of {{ProductName}}.

		>	**Note:** During migration the editor creates a .backup file containing the original contents of each migrated file. You can remove these files after successfully migrating your project.

		>	**Note:** A *.stingray_project* file and a *project.settings* file are created for each project that you migrate.

	-	Click **No**.

		The editor does not migrate your project, and does not open it.

You also have the option to **Remove** or **Delete** a project. Removing a project removes it from the *Projects* area of the **My Projects** tab but leaves the project data in the disk, while deleting a project removes the entire project and its data from the disk.

---
Related topics:
- ~{ Download assets and example projects }~
---
