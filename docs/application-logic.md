## Application state management

### Initial implementation

In the initial implementation, customer and order information was written directly to SharePoint during the ordering process.

This approach introduced unnecessary data writes and could leave incomplete records when users abandoned the ordering process.

### Improved implementation

The order creation logic was redesigned to maintain order information in a global record variable (`gblOrderDetails`).

The variable is updated throughout the ordering process, allowing users to navigate between screens without losing previously entered information.

Customer profile information is used to populate form fields when a new order is started. Once order information exists in application memory, the form uses the stored values instead.

```powerfx
If(
    IsBlank(gblOrderDetails);
    Asiakas.Kustannuspaikka;
    gblOrderDetails.Tilaajatili.Kustannuspaikka
)
```

This example demonstrates how the default value of a form field is determined based on the current order state.

### Benefits

- Reduced unnecessary SharePoint write operations
- Improved consistency of application state
- Preservation of user input between screens
- Reduced risk of incomplete records from abandoned orders
- Improved maintainability of the ordering logic

### Order creation process

flowchart TD
    A[Start new order] --> B[Load customer profile]
    B --> C[Enter customer details]
    C --> D{Valid input?}
    D -->|No| C
    D -->|Yes| E[Select products]
    E --> F[Review shopping cart]
    F --> G{Confirm order?}
    G -->|Continue editing| E
    G -->|Yes| H[Save order to SharePoint]
    H --> I{Successful?}
    I -->|No| J[Error handling]
    I -->|Yes| K[Clear application state]
    K --> L[Display order confirmation]
