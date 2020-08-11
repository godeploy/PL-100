# **Lab 03 – Canvas app**

## **What you will learn**

  - > Import and use a pre-built component library

  - > Create a Power Apps canvas app

  - > Connect to a data source

  - > Filter data

  - > Create data records

  - > Use images with data records

## **High-level lab steps**

  - > Exercise 1 – Import company components

  - > Exercise 2 – Create app and layout main screen (including list of my items)

  - > Exercise 3 – Submit New Report

## **Prerequisites**

Must have completed Lab 02 data modeling

Table of Contents

[Lab 03 – Canvas app 1](#lab-03-canvas-app)

[**What you will learn** 1](#what-you-will-learn)

[**High-level lab steps** 1](#high-level-lab-steps)

[**Prerequisites** 1](#prerequisites)

[**Exercise 1: Create canvas application** 3](#exercise-1-create-canvas-application)

[**Task 1: Import component library solution** 3](#task-1-import-component-library-solution)

[**Task 2: Create view** 4](#task-2-create-view)

[**Task 3: Create the user application** 5](#task-3-create-the-user-application)

[**Exercise 2: My reports** 10](#exercise-2-my-reports)

[**Task 1: Add gallery** 10](#task-1-add-gallery)

[**Exercise 3: Allow removing reports** 12](#exercise-3-allow-removing-reports)

[**Task 1: Allow remove** 12](#task-1-allow-remove)

[**Exercise 4: Add new report** 13](#exercise-4-add-new-report)

[**Task 1: Add new report form** 13](#task-1-add-new-report-form)

[**Exercise 5: Test the application** 16](#exercise-5-test-the-application)

[**Task 1: Test application** 16](#task-1-test-application)

## **Exercise 1: Create canvas application**

In this exercise, you will import a solution with shared components, create a view for the problem report entity, and create a canvas application.

### **Task 1: Import component library solution**

In this task, you will import the shared components solution into your environment. This shared component library was built by another team at your company.

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) page and make sure you are in the correct environment.

2.  Select **Solutions** and click **Import**.

![Import solution - screenshot](./media/image1.png)

3.  Click **Choose File**.

4.  Go to the course resources folder, select the **Shared components** solution, and click **Open**.

5.  Click **Next**.

6.  Click **Import**.

7.  Click **Publish All Customizations** and wait for the publishing to complete.

8.  Click **Close**.

9.  You should now see the **Shared Components** solution you imported. Click to open the **Shared Components** solution you imported.

10. The solution should have one item in it, **Lamna Healthcare Shared Components**.

![Imported solution components - screenshot](./media/image2.png)

### **Task 2: Create view**

In this task, you will create a view that will show the current user’s problem reports. Later you will use this view with the filter function in the canvas app.

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) page and make sure you are in the correct environment.

<!-- end list -->

1.  Select **Solutions** and click to open the **Company 311** solution.

<!-- end list -->

2.  Locate and click to open the **Problem Reports** entity.

3.  Select the **Views** tab and click to open the **Active Problem Reports** view.

![Open view - screenshot](./media/image3.png)

4.  Click **Edit filters**.

![Edit filters - screenshot](./media/image4.png)

5.  Change the filter to **Created By Equals current user** and click **OK**.

![Edit filter - screenshot](./media/image5.png)

6.  Click on the chevron button next to the Save button and select **Save As**.

![Save view as - screenshot](./media/image6.png)

7.  Enter **My Reports** for **Name** and click **Save**.

8.  Click **Publish** and wait for the publishing to complete.

9.  Click on the **Back** button.

### **Task 3: Create the user application**

In this task, you will create a canvas application using the phone form factor.

1.  Navigate to the [Power Apps maker portal](https://make.powerapps.com/) page and make sure you are in the correct environment.

2.  Select **Solutions** and click to open the **Company 311** solution.

3.  Click **+ New | App |Canvas app | Phone form factor**.

![Create canvas appellation - screenshot](./media/image7.png)

4.  Click **Skip** on the welcome screen.

5.  Select your **Region/Country** and click **Get started**.

6.  Click **File** and select **Save**.

7.  Enter **Company 311 Phone App** for name and click **Save**.

8.  Click on the back button.

![Back to app designer - screenshot](./media/image8.png)

9.  Go to the Tree view and double click **Screen1**.

![Edit screen name - screenshot](./media/image9.png)

10. Rename the screen **Main Screen**. It’s always a good idea to give your screens a meaningful name.

![Rename screens - screenshot](./media/image10.png)

11. Select the **Main Screen** and click **Insert**.

![Insert component - screenshot](./media/image11.png)

12. Expand **Custom**, select **Header Control** and **Tab Control**. These are both components from the library you imported earlier in the lab.

![Select controls - screenshot ](./media/image12.png)

13. Move the **Tab Control** to the bottom of the screen and the **Header Control** to the top of the screens.

14. Select the **Header Control** and change the **Text** value to **"Company 311".**

![Change text value - screenshot](./media/image13.png)

15. Right click on the Main Screen and select Duplicate screen.

![Duplicate screens - screenshot](./media/image14.png)

16. Rename the new screen **My Reports Screen**.

17. Select the **Tree view**, select **App** and change the **OnStart** value to the formula below. This formula will create a new variable named My Tabs and set it to a table of tab items.

Set('My Tabs', Table( {

Label: "My Reports",

Screen: 'Main Screen',

Icon: "",

SelectedIcon:""

},

{

Label: "New Report",

Screen: 'New Report Screen',

Icon: "",

SelectedIcon:""

}

))

![tab data variable - screenshot](./media/image15.png)

18. Select the **Tab Control** in the **Main Screen** and change the **Items** value to **‘My Tabs’**.

![Set tab items - screenshot](./media/image16.png)

19. Change the **SelectedColor** value to **WhiteSmoke**.

20. Select the **Tab Control** inside the **New Report Screen** and set the Item value to **‘My Tabs’**.

21. Change the **SelectedColor** value to **WhiteSmoke**.

22. Click on the **…** button of the **App** and select **Run OnStart**.

![Run app on start - screenshot](./media/image17.png)

23. Your tabs should now show the two tabs you added.

![Tab with data - screenshot](./media/image18.png)

25\. Do not navigate away from this page.

## **Exercise 2: My reports**

In this exercise, you will add a gallery that will show reports created by the current logged in user.

### **Task 1: Add gallery**

1.  Select the **Main Screen**, go to the **Insert** tab, click **Gallery**, and select **Vertical**.

![Insert gallery - screenshot](./media/image19.png)

2.  Rename the new gallery **My Reports Gallery**.

3.  Resize and reposition **My Reports Gallery** and make sure the screen looks like the image below.

![Gallery positioning - screenshot](./media/image20.png)

4.  Select **My Reports Gallery**, go to the **Properties** pane, and select **Problem Reports** for **Data Source**. If you do not see Problem Reports, click See all entities.

![Gallery data source - screenshot](./media/image21.png)

5.  Select the **My Reports** view you created for **View**.

6.  Click **Edit Fields**.

![Edit gallery fields - screenshot](./media/image22.png)

7.  Change Subtitle1 to **statuscode**. This is the Status Reason field.

![Edit field - screenshot ](./media/image23.png)

8.  Click File and then click Save.

9.  Click on the Back button.

10. Do not navigate away from this page.

## **Exercise 3: Allow removing reports**

In this exercise, you will allow unassigned reports to be removed. This will allow users to easily remove any accidental reports.

### **Task 1: Allow remove**

1.  Select the **Main Screen**, go to the **Insert** tab, click **Gallery**, and select **Vertical**.

2.  Select the **Icon** inside the **My Reports Gallery**.

![Select icon - screenshot](./media/image24.png)

3.  Change the **Icon** value to **Icon.Trash**.

![Change icon - screenshot](./media/image25.png)

4.  Change the **Visible** value to the formula below. This formula will hide the icon if the status reason is not New.

If(Text(ThisItem.'Status Reason') = "New", true, false)

![Change visible value - screenshot](./media/image26.png)

5.  Make sure you still have the icon selected. Change the **OnSelect** value to the formula below. This formula will remove item from the data source.

Remove('Problem Reports', ThisItem)

6.  Click **File** and then click **Save**.

7.  Do not navigate away from this page.

## **Exercise 4: Add new report**

In this exercise, you will add a form to submit new problem reports.

### **Task 1: Add new report form**

1.  Select the **New Report Screen**, go to the **Insert** tab, click **Form**, and select **Edit**.

![Insert edit form - screenshot](./media/image27.png)

2.  Rename the form **New Report Form**.

3.  Select **New Report Form**, go to the **Properties** pane, and select **Problem Report** for **Data source**.

4.  Click **Edit fields**.

![Edit form fields - screenshot](./media/image28.png)

5.  Remove the **Status Reason** field.

![Remove fields from form - screenshot](./media/image29.png)

6.  Remove the **Created On** field.

7.  Remove the **Location** field.

8.  Click **+ Add field**.

9.  Select **Details**, **Building**, **Department**, and **Photo**, and then click **Add**.

![Add fields to form - screenshot](./media/image30.png)

10. Resize and reposition the form so it takes most of the page and leave enough room for a button in the bottom.

![New report form - screenshot](./media/image31.png)

11. Select the **New Report Screen**.

12. Go to the **Insert** tab and select **Button**.

13. Rename the button **Submit Report**.

14. Place the button below the form and make it stretch across the screen

15. Change the **Submit Report** button text to **Submit**

16. Select the Submit Report button and change the **OnSelect** value to the formula below. This formula will create a new record and clear the form when the button is clicked.

SubmitForm('New Report Form'); NewForm('New Report Form')

17. Select the **New Report Form**.

18. Change the **OnSuccess** value to the formula below. This formula will show a notification after the new record gets created.

Notify("Created new problem report record")

19. Select the **New Report Screen**.

20. Set the **OnVisible** value to the formula below. This formula will create a new form when the screen becomes visible.

NewForm('New Report Form')

21. Click **File** and then click **Save**.

22. Click on button.

23. Do not navigate away from this page.

## **Exercise 5: Test the application**

In this exercise, you will test the canvas application you created by submitting a problem report.

### **Task 1: Test application**

1.  Select the **Main Screen** and click **Preview the app**.

![Preview application - screenshot](./media/image32.png)

2.  The application should load, and the list should show all the reports you created.

![Main screen - screenshot](./media/image33.png)

3.  Select the **New Report** tab.

4.  The **New Report Form** should load. Fill out the form and click on the **Photo** field.

5.  Select an image.

6.  Click **Submit**

7.  The record should get created successfully and you should see the success message.

![Save record message - screenshot](./media/image34.png)

8.  Select the **My Reports** tab.

9.  You should see the new report you created. Click **Delete** to test the delete.

![Delete record - screenshot](./media/image35.png)

10. The record should be deleted and removed from the list.

![Record list after deletion - screenshot](./media/image36.png)

11. Close the application.
