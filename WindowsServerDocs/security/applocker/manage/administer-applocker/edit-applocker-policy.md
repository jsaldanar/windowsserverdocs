---
title: Edit an applocker Policy
ms.custom: na
ms.prod: windows-server-2012
ms.reviewer: na
ms.suite: na
ms.technology: 
  - techgroup-security
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: df5a618f-141a-4435-b496-13274b7bd7e5
---
# Edit an applocker Policy
This topic describes the steps you need to perform to modify an applocker policy in  Windows Server 2012  and Windows 8.

You can edit an applocker policy by adding, changing, or removing rules. However, you cannot create a new version of the policy by importing additional rules. To modify an applocker policy that is in production, you should use Group Policy management software that allows you to version Group Policy Objects \(GPOs\). If you have created multiple applocker policies and need to merge them to create one applocker policy, you can either manually merge the policies or use the Windows PowerShell cmdlets for applocker. You cannot automatically merge policies by using the applocker snap\-in. You must create one rule collection from two or more policies. The applocker policy is saved in XML format, and the exported policy can be edited with any text or XML editor. For information about merging policies, see [Merge applocker Policies Manually]() or [Merge applocker Policies by Using Set-applockerPolicy]().

There are two methods you can use to edit an applocker policy:

-   [Editing an applocker policy by using Group Policy](#BKMK_EditAppPolinGPO)

-   [Editing an applocker policy by using the Local Security Policy snap\-in](#BKMK_EditAppLolNotinGPO)

## <a name="BKMK_EditAppPolinGPO"></a>Editing an applocker policy by using Group Policy
The steps to edit an applocker policy distributed by Group Policy include the following:

### Step 1: Use Group Policy management software to export the applocker policy from the GPO
applocker provides a feature to export and import applocker policies as an XML file. This allows you to modify an applocker policy outside your production environment. Because updating an applocker policy in a deployed GPO could have unintended consequences, you should first export the applocker policy to an XML file. For the procedure to do this, see [Export an applocker Policy from a GPO]().

### Step 2: Import the applocker policy into the applocker reference computer or the computer you use for policy maintenance
After exporting the applocker policy to an XML file, you should import the XML file onto a reference computer so that you can edit the policy. For the procedure to import an applocker policy, see [Import an applocker Policy from Another Computer]().

> [!CAUTION]
> Importing a policy onto another computer will overwrite the existing policy on that computer.

### Step 3: Use applocker to modify and test the rule
applocker provides ways to modify, delete, or add rules to a policy by modifying the rules within the collection.

-   For the procedure to modify a rule, see [Edit applocker Rules]().

-   For the procedure to delete a rule, see [Delete an applocker Rule]().

-   For procedures to create rules, see:

    -   [Create a Rule That Uses a Publisher Condition]()

    -   [Create a Rule That Uses a Path Condition]()

    -   [Create a Rule That Uses a File Hash Condition]()

    -   [Enable the DLL Rule Collection]()

-   For steps to test an applocker policy, see [Test and Update an applocker Policy](test-update-applocker-policy.md).

-   For procedures to export the updated policy from the reference computer back into the GPO, see [Export an applocker Policy to an XML File]() and [Import an applocker Policy into a GPO]().

### Step 4: Use applocker and Group Policy to import the applocker policy back into the GPO
For procedures to export the updated policy from the reference computer back into the GPO, see [Export an applocker Policy to an XML File]() and [Import an applocker Policy into a GPO]().

> [!CAUTION]
> You should never edit an applocker rule collection while it is being enforced in Group Policy. Because applocker controls what files are allowed run, making changes to a live policy can create unexpected behavior. For information about testing policies, see [Test and Update an applocker Policy](test-update-applocker-policy.md).

> [!NOTE]
> If you are performing these steps by using Microsoft Advanced Group Policy Management \(AGPM\), check out the GPO before exporting the policy.

## <a name="BKMK_EditAppLolNotinGPO"></a>Editing an applocker policy by using the Local Security Policy snap\-in
The steps to edit an applocker policy distributed by using the Local Security Policy snap\-in include the following tasks.

### Step 1: Import the applocker policy
On the computer where you maintain policies, open the applocker snap\-in from the Local Security Policy snap\-in. If you exported the applocker policy from another computer, use applocker to import it onto the computer.

After exporting the applocker policy to an XML file, you should import the XML file onto a reference computer so that you can edit the policy. For the procedure to import an applocker policy, see [Import an applocker Policy from Another Computer]().

> [!CAUTION]
> Importing a policy onto another computer will overwrite the existing policy on that computer.

### Step 2: Identify and modify the rule to change, delete, or add
applocker provides ways to modify, delete, or add rules to a policy by modifying the rules within the collection.

-   For the procedure to modify a rule, see [Edit applocker Rules]().

-   For the procedure to delete a rule, see [Delete an applocker Rule]().

-   For procedures to create rules, see:

    -   [Create a Rule That Uses a Publisher Condition]()

    -   [Create a Rule That Uses a Path Condition]()

    -   [Create a Rule That Uses a File Hash Condition]()

    -   [Enable the DLL Rule Collection]()

### Step 3: Test the effect of the policy
For steps to test an applocker policy, see [Test and Update an applocker Policy](test-update-applocker-policy.md).

### Step 4: Export the policy to an XML file and propagate it to all targeted computers
For procedures to export the updated policy from the reference computer to targeted computers, see [Export an applocker Policy to an XML File]() and [Import an applocker Policy from Another Computer]().

## Additional resources

-   For steps to perform other applocker policy tasks, see [Administer applocker]().

## See Also
[applocker Overview \[Client\]](assetId:///1637ae87-5059-4d95-8c68-96f35cbc88c7)

