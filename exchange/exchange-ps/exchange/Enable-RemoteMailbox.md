---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016
schema: 2.0.0
---

# Enable-RemoteMailbox

## SYNOPSIS
!!! Exchange Server 2010

Use the Enable-RemoteMailbox cmdlet to create a mailbox in the cloud-based service for an existing user in the on-premises Active Directory.

!!! Exchange Server 2013, Exchange Server 2016

This cmdlet is available only in on-premises Exchange.

Use the Enable-RemoteMailbox cmdlet to create a mailbox in the cloud-based service for an existing user in the on-premises Active Directory.

For information about the parameter sets in the Syntax section below, see Exchange cmdlet syntax (https://technet.microsoft.com/library/bb123552.aspx).

## SYNTAX

### Set4
```
Enable-RemoteMailbox [-Identity] <UserIdParameter> [-Equipment] [-Alias <String>] [-Confirm]
 [-DisplayName <String>] [-DomainController <Fqdn>] [-PrimarySmtpAddress <SmtpAddress>]
 [-RemoteRoutingAddress <ProxyAddress>] [-WhatIf] [-ACLableSyncedObjectEnabled] [<CommonParameters>]
```

### Set2
```
Enable-RemoteMailbox [-Identity] <UserIdParameter> [-Room] [-Alias <String>] [-Confirm] [-DisplayName <String>]
 [-DomainController <Fqdn>] [-PrimarySmtpAddress <SmtpAddress>] [-RemoteRoutingAddress <ProxyAddress>]
 [-WhatIf] [-ACLableSyncedObjectEnabled] [<CommonParameters>]
```

### Set5
```
Enable-RemoteMailbox [-Identity] <UserIdParameter> [-Alias <String>] [-Archive]
 [-ArchiveName <MultiValuedProperty>] [-Confirm] [-DisplayName <String>] [-DomainController <Fqdn>]
 [-PrimarySmtpAddress <SmtpAddress>] [-WhatIf] [-ACLableSyncedObjectEnabled] [<CommonParameters>]
```

### Set1
```
Enable-RemoteMailbox [-Identity] <UserIdParameter> [-Alias <String>] [-Confirm] [-DisplayName <String>]
 [-DomainController <Fqdn>] [-PrimarySmtpAddress <SmtpAddress>] [-RemoteRoutingAddress <ProxyAddress>]
 [-WhatIf] [-ACLableSyncedObjectEnabled] [<CommonParameters>]
```

### Set3
```
Enable-RemoteMailbox [-Identity] <UserIdParameter> [-Alias <String>] [-Confirm] [-DisplayName <String>]
 [-DomainController <Fqdn>] [-PrimarySmtpAddress <SmtpAddress>] [-RemoteRoutingAddress <ProxyAddress>]
 [-WhatIf] [-Equipment] [-ACLableSyncedObjectEnabled] [<CommonParameters>]
```

## DESCRIPTION
!!! Exchange Server 2010

The Enable-RemoteMailbox cmdlet mail-enables an existing on-premises user. The mail-enabled user contains a specific attribute that indicates that an associated mailbox in the service should be created when the user is synchronized to the service using directory synchronization.

Directory synchronization must be configured correctly for a mailbox to be created in the service. Creation of the mailbox in the service isn't immediate and depends on the directory synchronization schedule.

For more information about remote mailboxes, see Understanding Recipients.

The policies that you apply to recipients in the on-premises Exchange organization, such as Unified Messaging or compliance policies, aren't applied to mailboxes in the service. You must configure policies in the service if you want policies to be applied to recipients in the service.

You need to be assigned permissions before you can run this cmdlet. Although all parameters for this cmdlet are listed in this topic, you may not have access to some parameters if they're not included in the permissions assigned to you. To see what permissions you need, see the "Remote mailboxes" entry in theMailbox Permissions topic.

!!! Exchange Server 2013

The Enable-RemoteMailbox cmdlet mail-enables an existing on-premises user. The mail-enabled user contains a specific attribute that indicates that an associated mailbox in the service should be created when the user is synchronized to the service using directory synchronization.

Directory synchronization must be configured correctly for a mailbox to be created in the service. Creation of the mailbox in the service isn't immediate and depends on the directory synchronization schedule.

The policies that you apply to recipients in the on-premises Exchange organization, such as Unified Messaging or compliance policies, aren't applied to mailboxes in the service. You must configure policies in the service if you want policies to be applied to recipients in the service.

You need to be assigned permissions before you can run this cmdlet. Although all parameters for this cmdlet are listed in this topic, you may not have access to some parameters if they're not included in the permissions assigned to you. To see what permissions you need, see the "Remote mailboxes" entry in the Recipients Permissions topic.

!!! Exchange Server 2016

The Enable-RemoteMailbox cmdlet mail-enables an existing on-premises user. The mail-enabled user contains a specific attribute that indicates that an associated mailbox in the service should be created when the user is synchronized to the service using directory synchronization.

Directory synchronization must be configured correctly for a mailbox to be created in the service. Creation of the mailbox in the service isn't immediate and depends on the directory synchronization schedule.

The policies that you apply to recipients in the on-premises Exchange organization, such as Unified Messaging or compliance policies, aren't applied to mailboxes in the service. You must configure policies in the service if you want policies to be applied to recipients in the service.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see Find the permissions required to run any Exchange cmdlet (https://technet.microsoft.com/library/mt432940.aspx).

## EXAMPLES

### Example 1 -------------------------- (Exchange Server 2010)
```
Enable-RemoteMailbox "Kim Akers"
```

This example mail-enables an existing on-premises user and creates an associated mailbox in the service. The remote routing address doesn't need to be specified because mail flow between the on-premises organization and the service has been configured. Using this configuration, the Enable-RemoteMailbox cmdlet automatically calculates the SMTP address of the mailbox to be used with the RemoteRoutingAddress parameter. This example also assumes directory synchronization has been configured.


To mail-enable an existing user and create an associated mailbox in the service, run the New-RemoteMailbox cmdlet and specify the identity of the existing user.

After the user is mail-enabled, directory synchronization synchronizes the mail-enabled user to the service and the associated mailbox is created.

### Example 1 -------------------------- (Exchange Server 2013)
```
Enable-RemoteMailbox "Kim Akers" -RemoteRoutingAddress "kima@contoso.mail.onmicrosoft.com
```

This example mail-enables an existing on-premises user and creates an associated mailbox in the service.


To mail-enable an existing user and create an associated mailbox in the service, run the New-RemoteMailbox cmdlet and specify the identity of the existing user.

After the user is mail-enabled, directory synchronization synchronizes the mail-enabled user to the service and the associated mailbox is created.

### Example 1 -------------------------- (Exchange Server 2016)
```
Enable-RemoteMailbox "Kim Akers" -RemoteRoutingAddress "kima@contoso.mail.onmicrosoft.com"
```

This example mail-enables an existing on-premises user and creates an associated mailbox in the service.


To mail-enable an existing user and create an associated mailbox in the service, run the New-RemoteMailbox cmdlet and specify the identity of the existing user.

After the user is mail-enabled, directory synchronization synchronizes the mail-enabled user to the service and the associated mailbox is created.

### Example 2 -------------------------- (Exchange Server 2010)
```
Enable-RemoteMailbox "Kim Akers" -Archive
```

This example does the following:


Mail-enables an existing on-premises user.

Creates the associated mailbox in the service.

Creates an archive mailbox in the service for the mailbox.

As in Example 1, this example assumes that mail flow and directory synchronization have been properly configured.


To mail-enable an on-premises user, create the associated mailbox in the service, enable the archive mailbox in the service, and include the Archive switch with the Enable-RemoteMailbox cmdlet.

### Example 2 -------------------------- (Exchange Server 2013)
```
Enable-RemoteMailbox "Kim Akers" -RemoteRoutingAddress "kima@contoso.mail.onmicrosoft.com -Archive
```

This example does the following:


Mail-enables an existing on-premises user.

Creates the associated mailbox in the service.

Creates an archive mailbox in the service for the mailbox.

To mail-enable an on-premises user, create the associated mailbox in the service, enable the archive mailbox in the service, and include the Archive switch with the Enable-RemoteMailbox cmdlet.

### Example 2 -------------------------- (Exchange Server 2016)
```
Enable-RemoteMailbox "Kim Akers" -RemoteRoutingAddress "kima@contoso.mail.onmicrosoft.com" -Archive
```

This example does the following:


Mail-enables an existing on-premises user.

Creates the associated mailbox in the service.

Creates an archive mailbox in the service for the mailbox.

To mail-enable an on-premises user, create the associated mailbox in the service, enable the archive mailbox in the service, and include the Archive switch with the Enable-RemoteMailbox cmdlet.

## PARAMETERS

### -Identity
!!! Exchange Server 2010

The Identity parameter takes one of the following values:

- ADObjectID

- GUID

- Distinguished name (DN)

- Domain\\SamAccountName

- User principal name (UPN)

- LegacyExchangeDN

- User alias



!!! Exchange Server 2013

The Identity parameter specifies the identity of the existing on-premises user. The Identity parameter can have one of the following values:

- ADObjectID

- GUID

- Distinguished name (DN)

- Domain\\SamAccountName

- User principal name (UPN)

- LegacyExchangeDN

- User alias



!!! Exchange Server 2016

The Identity parameter specifies the identity of the existing on-premises user. You can use any value that uniquely identifies the user. For example:

- ADObjectID

- GUID

- Distinguished name (DN)

- Domain\\SamAccountName

- User principal name (UPN)

- LegacyExchangeDN

- User alias



```yaml
Type: UserIdParameter
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: True
Position: 1
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -Equipment
The Equipment switch specifies that the mailbox in the service should be created as an equipment resource mailbox.

You can't use the Equipment switch if you specified the Room switch.

```yaml
Type: SwitchParameter
Parameter Sets: Set4, Set3
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Room
!!! Exchange Server 2010, Exchange Server 2013

The Room switch specifies that the mailbox in the service should be created as a room resource mailbox.

You can't use the Room switch if you specified the Equipment switch.



!!! Exchange Server 2016

The Room switch specifies that the mailbox in the service should be created as a room resource mailbox. You don't need to specify a value with this switch

You can't use this switch with the Equipment switch.



```yaml
Type: SwitchParameter
Parameter Sets: Set2
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Alias
!!! Exchange Server 2010, Exchange Server 2013

The Alias parameter specifies the alias of the user and its associated mailbox in the service. An alias can contain letters, numbers, and the following punctuation marks and symbols:

- !

- #

- $

- %

- ^

- &

- \*

- +

- -

- .

- /

- =

- ?

- \_

- {

- }

- |

- ~



!!! Exchange Server 2016

The Alias parameter specifies the Exchange alias (also known as the mail nickname) for the recipient. This value identifies the recipient as a mail-enabled object, and shouldn't be confused with multiple email addresses for the same recipient (also known as proxy addresses). A recipient can have only one Alias value.

The value of Alias can contain letters, numbers and the characters !, #, $, %, &, ', \*, +, -, /, =, ?, ^, \_, `, {, |, } and ~. Periods (.) are allowed, but each period must be surrounded by other valid characters (for example, help.desk). Unicode characters from U+00A1 to U+00FF are also allowed. The maximum length of the Alias value is 64 characters.

When you create a recipient without specifying an email address, the Alias value you specify is used to generate the primary email address (\<alias\>@\<domain\>). Supported Unicode characters are mapped to best-fit US-ASCII text characters. For example, U+00F6 (ö) is changed to oe in the primary email address.

If you don't use the Alias parameter when you create a recipient, the value of a different required parameter is used for the Alias property value:

- Recipients with user accounts (for example, user mailboxes, and mail users): The left side of the MicrosoftOnlineServicesID or UserPrincipalName parameter is used. For example, helpdesk@contoso.com results in the Alias property value helpdesk.

- Recipeints without user accounts (for example, room mailboxes, mail contacts, and distribution groups): The value of the Name parameter is used. Spaces are removed and unsupported characters are converted to question marks (?).

If you modify the Alias value of an existing recipient, the primary email address is automatically updated only in on-premises environments where the recipient is subject to email address policies (the EmailAddressPolicyEnabled property is True for the recipient).

The Alias parameter never generates or updates the primary email address of a mail contact or a mail user.



```yaml
Type: String
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Archive
!!! Exchange Server 2010, Exchange Server 2013

The Archive switch specifies whether to create an archive mailbox in the service in addition to the mailbox created in the service.

You don't have to specify a value with this switch.



!!! Exchange Server 2016

The Archive switch specifies whether to create an archive mailbox in the service in addition to the mailbox created in the service.

You don't need to specify a value with this switch.



```yaml
Type: SwitchParameter
Parameter Sets: Set5
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ArchiveName
The ArchiveName parameter specifies the name of the archive mailbox. Use this parameter to change the name of the archive.

```yaml
Type: MultiValuedProperty
Parameter Sets: Set5
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
The Confirm switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding.

- Destructive cmdlets (for example, Remove-\* cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: -Confirm:$false.

- Most other cmdlets (for example, New-\* and Set-\* cmdlets) don't have a built-in pause. For these cmdlets, specifying the Confirm switch without a value introduces a pause that forces you acknowledge the command before proceeding.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
!!! Exchange Server 2010, Exchange Server 2013

The DisplayName parameter specifies the display name for the mailbox that's created in the service.



!!! Exchange Server 2016

The DisplayName parameter specifies the display name for the mailbox that's created in the service. The display name is visible in the Exchange admin center, address lists, and Outlook. The maximum length is 256 characters. If the value contains spaces, enclose the value in quotation marks (").



```yaml
Type: String
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainController
The DomainController parameter specifies the domain controller that's used by this cmdlet to read data from or write data to Active Directory. You identify the domain controller by its fully qualified domain name (FQDN). For example, dc01.contoso.com.

```yaml
Type: Fqdn
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimarySmtpAddress
!!! Exchange Server 2010

The PrimarySmtpAddress parameter specifies the primary SMTP address for the mail user. By default, the primary SMTP address is generated based on the default e-mail address policy. If you specify a primary SMTP address by using this parameter, the cmdlet sets the EmailAddressPolicyEnabled attribute of the mail user to $false, and the e-mail addresses of this mail user aren't automatically updated based on e-mail address policies.



!!! Exchange Server 2013

The PrimarySmtpAddress parameter specifies the primary SMTP address for the mail user. By default, the primary SMTP address is generated based on the default email address policy. If you specify a primary SMTP address by using this parameter, the cmdlet sets the EmailAddressPolicyEnabled attribute of the mail user to $false, and the email addresses of this mail user aren't automatically updated based on email address policies.



!!! Exchange Server 2016

The PrimarySmtpAddress parameter specifies the primary return email address that's used for the recipient. If it's available on this cmdlet, you can't use the EmailAddresses and PrimarySmtpAddress parameters in the same command.



```yaml
Type: SmtpAddress
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoteRoutingAddress
!!! Exchange Server 2010

The RemoteRoutingAddress parameter specifies the SMTP address of the mailbox in the service that this user is associated with.

If you've configured mail flow between the on-premises organization and the service, you don't need to specify this parameter. The remote routing address is calculated automatically.



!!! Exchange Server 2013, Exchange Server 2016

The RemoteRoutingAddress parameter specifies the SMTP address of the mailbox in the service that this user is associated with.



```yaml
Type: ProxyAddress
Parameter Sets: Set4, Set2, Set1, Set3
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
The WhatIf switch simulates the actions of the command. You can use this switch to view the changes that would occur without actually applying those changes. You don't need to specify a value with this switch.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ACLableSyncedObjectEnabled
This parameter is reserved for internal Microsoft use.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/p/?LinkID=113216).

## INPUTS

###  
To see the input types that this cmdlet accepts, see Cmdlet Input and Output Types (https://go.microsoft.com/fwlink/p/?LinkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data.

## OUTPUTS

###  
To see the return types, which are also known as output types, that this cmdlet accepts, see Cmdlet Input and Output Types (https://go.microsoft.com/fwlink/p/?LinkId=616387). If the Output Type field is blank, the cmdlet doesn't return data.

## NOTES

## RELATED LINKS

[Online Version](https://technet.microsoft.com/library/63a504e5-c1ee-4812-921f-d461e24afa1b.aspx)
