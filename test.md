# Email Template – Unsupported Macros by Template Code

Your **50+ templates** in admin each have a **Template Code** (e.g. `OrderReceipt`, `EmailAFriend`). That code determines which code path runs and therefore **which macros are supported**. Use the table below to find your template by code.

**Rules:**
- **Supported** = macro is replaced with a value in that template’s code path.
- **Unsupported** = macro is either replaced with **empty** (when `ReplaceTemplateTokens(empty)` is used) or left as **literal** `#MacroName#` in the email.
- **#StoreName#** vs **#SiteName#**: Order/Quote receipts use **#SiteName#** (store name); they do **not** replace **#StoreName#**.

---

## Master list: Template Code → Supported vs Unsupported macros

| # | Template Code | Supported macros (only these work) | Unsupported (empty or literal) |
|---|----------------|------------------------------------|--------------------------------|
| 1 | **EmailAFriend** | #ProductLink#, #CatalogName#, #StoreName#, #StoreLogo#, #StoreURL# | All other macros from the standard list |
| 2 | **ProductComparisonDetails** | #CustomerServiceEmail#, #CustomerServicePhoneNumber#, #StoreLogo#, #StoreURL# | All others (incl. #StoreName#, #CatalogName#) |
| 3 | **ServiceRequestMessage** | #FirstName#, #EmailMessage#, #StoreLogo#, #StoreURL# | All others (incl. #StoreName#, #CatalogName#) |
| 4 | **ContactUs** | #FirstName#, #LastName#, #CompanyName#, #PhoneNumber#, #Comments#, #StoreLogo#, #StoreURL# | All others (incl. #StoreName#, #CatalogName#) |
| 5 | **CustomerFeedbackNotification** | #Message#, #FirstName#, #LastName#, #City#, #State#, #EmailAddress#, #ShareFeedback#, #Comments#, #StoreLogo#, #StoreURL# | All others (incl. #StoreName#, #CatalogName#) |
| 6 | **PendingApproval** | #QuoteId#, #QuoteApprover#, #ApproverComments#, #StoreLogo# | All others (incl. #StoreName#, #CatalogName#) – show as literal |
| 7 | **StatusApproved** | #QuoteId#, #CustomerName#, #ApproverComments#, #StoreLogo# | All others – literal |
| 8 | **StatusRejected** | #QuoteId#, #CustomerName#, #ApproverComments#, #StoreLogo# | All others – literal |
| 9 | **QuoteSentForApproval** | #QuoteId#, #CustomerName#, #StoreLogo# | All others – literal |
| 10 | **QuoteRequestAcknowledgementToUser** | #StoreLogo#, #StoreName#, #QuoteId#, #QuoteStatus#, #QuoteDate#, #ExpirationDate#, #OrderNumber#, #ReturnTotalExpectedQty#, #QuoteName#, #CustomerServiceEmail#, #CustomerServicePhoneNumber#, #BillingAddress#, #ShippingAddress#, #ShippingConstraintCode#, #InHandDate#, #ShippingName#, #TotalCost#, #UserName#, #StoreURL# | #CatalogName# and all others – literal |
| 11 | **QuoteConvertedToOrder** | Same as row 10 | Same as row 10 |
| 12 | **NewQuoteRequestNotificationForAdmin** | Same as row 10 | Same as row 10 |
| 13 | **RMA Return** (dynamic code per status) | #UserFullName#, #ReturnNumber#, #ReturnStatus#, #StoreName#, #Url#, #ReturnDate#, #ReturnTotalExpectedQty#, #ShippingTo#, #ShippingFrom#, #OrderNumber#, #CustomerName#, #CustomerServiceEmail#, #CustomerServicePhoneNumber#, #ReturnBarcode#, #TotalCost# | #CatalogName# and all others – empty |
| 14 | **RMARequestStatus** | #CustomerName#, #CustomerNotification#, #StoreName#, #DepartmentName#, #DepartmentAddress#, #DepartmentEmail#, #BillingEmailId# | #CatalogName# and all others – empty |
| 15 | **IssueGiftCard** | #FirstName#, #CardNumber#, #Amount#, #ExpirationDate#, #StoreName#, #DisplayName#, #Address#, #Email# | #CatalogName# and all others – empty |
| 16 | **FormBuilder** (dynamic code per form) | #StoreName# (if provided), #StoreLogo#, #CustomerServicePhoneNumber#, #CustomerServiceEmail#, #StoreURL#, + form-field macros | #CatalogName# and all others – literal |
| 17 | **OrderReceipt** | Receipt-based: #SiteName#, #StoreLogo#, #ReceiptText#, #CustomerServiceEmail#, #CustomerServicePhoneNumber#, #FeedBack#, #ShippingName#, #CardTransactionID#, #CardTransactionLabel#, #PaymentName#, #PONumber#, #PurchaseNumberLabel#, #OrderId#, #OrderDate#, #UserId#, #BillingAddress#, #ShippingAddress#, #PromotionCode#, #TotalCost#, #JobName#, #InHandDate#, #ShippingConstraintCode#, #BillingFirstName#, #BillingLastName#, #AdditionalInstructions#, #TrackingNumber#, #TrackingMessage#, #Message#, #Name#, #SKU#, #Quantity#, #Description#, #UOMDescription#, #Price#, #ExtendedPrice#, #ShortDescription#, #Title#, #Amount#, #ReturnedTitle#, #ReturnedPrice#, #AccountNumber#, etc. | #StoreName# (use #SiteName#), #CatalogName#, #ProductLink#, #ShipmentNo#, #ShipTo#, and any macro not in receipt data |
| 18 | **ResendOrderReceipt** | Same handler as OrderReceipt (row 17) | Same as row 17 |
| 19 | **ProductKeyOrderReceipt** | Same receipt-style; product key specific | Same as row 17 |
| 20 | **ShippingReceipt** | Same receipt-style | Same as row 17 |
| 21 | **CancelledOrderReceipt** | Same receipt-style | Same as row 17 |
| 22 | **VendorReceipt** | Same receipt-style | Same as row 17 |
| 23 | **LowInventoryOrderNotification** | Receipt-style (CreateLowInventoryNotification) | Same as row 17 |
| 24 | **RemainingVoucherBalance** | #VoucherName#, #VoucherAmountUsed#, #RemainingAmount#, #CustomerName#, #GiftCardNumber#, #OrderNumber#, #StoreName#, #StoreURL# | #CatalogName# and all others not listed |
| 25 | **BillingAccountNumberAdded** | #CustomerName#, #StoreURL# | #StoreName#, #CatalogName#, #StoreLogo#, and all others – literal |
| 26 | **VoucherExpirationReminder** | (GiftCard flow; tokens may vary) | #CatalogName# and others not in that flow |
| 27 | **IssueVoucher** | #CustomerName#, #StoreName#, #VoucherName#, #GiftCardNumber#, #ExpirationDate#, #StoreLogo#, #FirstName#, #StartDate#, #StoreURL# | #CatalogName# and all others not listed |
| 28 | **SendWaitingListNoticeInInventory** | #ProductName#, #Emailaddress#, #Url#, #Image#, #ProductLink#, #SKU#, #StoreName#, #StoreURL# | #CatalogName# and all others |
| 29 | **ERPTaskSchedulerStatus** | #SchedulerName#, #TouchPointName#, #SchedulerStatus#, #ErrorMessage#, #StoreLogo# | #StoreName#, #CatalogName#, and all others – empty |
| 30 | **TrackingLinks** | #UserName#, #Links#, #StoreLogo# | #StoreName#, #CatalogName#, and all others – literal |
| 31 | **NewNewsletterSignupNotification** | (UserService; token set varies) | #StoreName#, #CatalogName# unless in dictionary |
| 32 | **CustomerNewsletterOnboarding** | (UserService) | Same as row 31 |
| 33 | **CustomerAccountActivation** | #BillingFirstName#, #StoreLogo#, #Url#, #StoreURL# | #StoreName#, #CatalogName#, and others – literal |
| 34 | **AccountDeActivation** | Same as row 33 | Same as row 33 |
| 35 | **RegistrationAttemptUsingExistingUsername** | (UserService dictionary) | Depends on SetParameter dictionary |
| 36 | **NewCustomerAccountFromAdmin** | #StoreName#, #FirstName#, #LastName#, #EmailAddress#, #DisplayName#, #Link#, #Url#, #Password#, #StoreLogo#, #CustomerServiceEmail#, #CustomerServicePhoneNumber#, #PhoneNumber#, #State#, #City#, #Email# (ResetPassword flow) | #CatalogName# and any not in dictionary |
| 37 | **ResetPassword** | Same as row 36 | Same as row 36 |
| 38 | **ConvertCustomerToAdministrator** | (UserService ReplaceTemplateTokens with dictionary) | #StoreName#, #CatalogName# unless in dictionary |
| 39 | **NewCustomerAccountFromWebstore** | Same handler as NewCustomerAccountFromAdmin | Same as row 36 |

---

## Quick reference: #StoreName# and #CatalogName#

| Template code(s) | #StoreName# | #CatalogName# |
|------------------|-------------|----------------|
| EmailAFriend | Supported | Supported |
| ProductComparisonDetails, ServiceRequestMessage, ContactUs, CustomerFeedbackNotification | **Unsupported** (empty) | **Unsupported** (empty) |
| PendingApproval, StatusApproved, StatusRejected, QuoteSentForApproval | **Unsupported** (literal) | **Unsupported** (literal) |
| QuoteRequestAcknowledgementToUser, QuoteConvertedToOrder, NewQuoteRequestNotificationForAdmin | Supported | **Unsupported** (literal) |
| RMA Return, RMARequestStatus, IssueGiftCard | Supported | **Unsupported** (empty) |
| FormBuilder | Supported (if storeName provided) | **Unsupported** (literal) |
| OrderReceipt, ShippingReceipt, etc. | **Use #SiteName#** (receipt data) | **Unsupported** |
| RemainingVoucherBalance, IssueVoucher, SendWaitingListNoticeInInventory | Supported | **Unsupported** |
| BillingAccountNumberAdded, ERPTaskSchedulerStatus, TrackingLinks, CustomerAccountActivation, etc. | **Unsupported** unless in that template’s dictionary | **Unsupported** |

---

*Generated from codebase analysis. Templates that call `ReplaceTemplateTokens` with an empty dictionary replace any unreplaced `#...#` token with empty string.*
