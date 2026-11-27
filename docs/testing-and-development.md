# Testing and development

## Iterative development

The project followed an iterative development approach, with requirements refined through customer meetings, demonstrations and feedback.

Existing functionality was continuously evaluated and improved throughout development.

## Functional testing

Manual test plans were created to verify application functionality and identify potential issues.

Testing covered areas such as:

- Order creation
- Customer information and form validation
- Navigation between ordering stages
- Shopping cart functionality
- Data persistence
- Automated notifications
- Error handling

### Example functional test cases

| Test ID | Test scenario | Expected result |
|---|---|---|
| TC-01 | Start an order with an existing customer profile | Form fields are prepopulated |
| TC-02 | Submit an invalid email address | Validation prevents proceeding |
| TC-03 | Leave a required field empty | Validation message is displayed |
| TC-04 | Navigate back to customer details | Previously entered information is preserved |
| TC-05 | Abandon an unconfirmed order | No order records are created |
| TC-06 | Confirm a valid order | Order data is saved to SharePoint |
| TC-07 | Successfully complete an order | Confirmation screen is displayed |
| TC-08 | Change order status to New | Confirmation email is triggered |
| TC-09 | Modify unrelated order information | No additional confirmation email is sent |
| TC-10 | Change order status to Ready for pickup | Pickup notification is triggered |

*These examples illustrate the functional testing approach used
during development and represent selected application scenarios.*

## Version management

Power Apps' built-in version history was used to manage application versions and restore previous versions when necessary.

## Technical documentation

Documentation was created to support system usage, maintenance and future development.

This included functional descriptions, technical system documentation, data model documentation and test plans.

## Future improvements

Potential areas for further development include:

- Solution-based development and deployment
- Application lifecycle management (ALM)
- Automated testing
- Enhanced data source security
- Improved environment configuration and connection management
