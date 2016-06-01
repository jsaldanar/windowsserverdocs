---
title: Federated Web SSO Design
ms.custom: 
  - AD
ms.prod: windows-server-2012
ms.reviewer: na
ms.suite: na
ms.technology: 
  - techgroup-identity
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 06180678-8a0a-4d68-86a7-e87efbc3f575
author: billmath
---
# Federated Web SSO Design
The Federated Web Single\-Sign\-On \(SSO\) design in [!INCLUDE[firstref_adfs2](includes/firstref_adfs2_md.md)] involves secure communication that spans multiple firewalls, perimeter networks, and name\-resolution servers—in addition to the entire Internet routing infrastructure.  
  
Typically, this design is used when two organizations agree to create a federation trust relationship to allow users in one organization \(the account partner organization\) to access Web\-based applications or services, which are secured by [!INCLUDE[nextref_adfs2](includes/nextref_adfs2_md.md)], in the other organization \(the resource partner organization\).  
  
In other words, a federation trust relationship is the embodiment of a business\-level agreement or partnership between two organizations. As shown in the following illustration, you can establish a federation trust relationship between two businesses, which results in an end\-to\-end federation scenario.  
  
![](media/adfs2_FederatedWebSSODesign.gif)  
  
The one\-way arrow in the illustration signifies the direction of the federation trust, which—like the direction of Windows trusts—always points to the account side of the forest. This means that authentication flows from the account partner organization to the resource partner organization.  
  
In this Federated Web SSO design, two [!INCLUDE[adfs2_fs](includes/adfs2_fs_md.md)]s \(one in Fabrikam and the other in Contoso\) route authentication requests from user accounts in Fabrikam to Web\-based applications or services in Contoso.  
  
> [!NOTE]  
> For additional security, you can use [!INCLUDE[adfs2_fs](includes/adfs2_fs_md.md)] proxies to relay requests to [!INCLUDE[adfs2_fs](includes/adfs2_fs_md.md)]s that are not directly accessible from the Internet.  
  
In this example, Fabrikam is the identity, or account, provider. The Fabrikam portion of the Federated Web SSO design uses the following [!INCLUDE[nextref_adfs2](includes/nextref_adfs2_md.md)] deployment goal:  
  
-   [Provide Your Active Directory Users Access to the Applications and Services of Other Organizations](Provide-Your-Active-Directory-Users-Access-to-the-Applications-and-Services-of-Other-Organizations.md)  
  
Contoso is the resource provider. The Contoso portion of the Federated Web SSO design achieves the following [!INCLUDE[nextref_adfs2](includes/nextref_adfs2_md.md)] deployment goals:  
  
-   [Provide Users in Another Organization Access to Your Claims-Aware Applications and Services](Provide-Users-in-Another-Organization-Access-to-Your-Claims-Aware-Applications-and-Services.md)  
  
-   [Provide Your Active Directory Users Access to Your Claims-Aware Applications and Services](Provide-Your-Active-Directory-Users-Access-to-Your-Claims-Aware-Applications-and-Services.md)  
  
For a list of detailed tasks that you can use to plan and deploy the Federated Web SSO design, see [Checklist: Implementing a Federated Web SSO Design](Checklist--Implementing-a-Federated-Web-SSO-Design.md).  
  
