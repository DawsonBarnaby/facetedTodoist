### Faceted Todoist Task Search
This repository contains a simple HTML/JavaScript application for performing a faceted search of Todoist tasks. Users can customize the search interface by modifying the provided HTML radio buttons and JavaScript configuration. It would be nice to make this configurable in future.

## Features
Dynamic Search Interface: Update the Todoist search results in real-time as users change the selected facets.
Customizable Facets: Modify the search facets to suit your specific needs by editing the HTML and JavaScript files.
## Getting Started
To use this application, follow these steps:

# 1. Clone the Repository
Clone the repository to your local machine using the standard gh cli tool.

# 2. Open the HTML File
Open index.html in your preferred web browser to see the search interface.

# 3. Customize the Search Interface
HTML Radio Buttons
Edit the HTML radio buttons to define your own search facets. Each radio button group should be enclosed in a div with the class radio-group and a data-group attribute that uniquely identifies the group. Each radio button within the group should have a name attribute matching the group's name and a value attribute defining the search term.

Example:

# Html configuration
```
<div class="radio-group" data-group="category">
    <label><input type="radio" name="category" value="all"> All</label>
    <label><input type="radio" name="category" value="planning"> Planning</label>
    <!-- Add more radio buttons as needed -->
</div>
```
# JavaScript Configuration
Edit the defaultSelections and queryMappings objects in the <script> section to match your new facets and their corresponding Todoist query mappings.

defaultSelections defines the default selected value for each facet.
queryMappings maps each facet value to a corresponding Todoist query.
Example:

```
// Default selections
const defaultSelections = {
    category: "active",
    timeframe: "due",
    availability: "anytime",
    location: "all"
};

// Query string mappings
const queryMappings = {
    category: {
        "all": "(p1 | ! p1)",
        "planning": "@planning",
        // Add more mappings as needed
    },
    timeframe: {
        "upcoming this week": "(overdue | next 7 days | no date)",
        // Add more mappings as needed
    },
    // Add more facets and mappings as needed
};
```
# 4. Save and Test
Save your changes and refresh the index.html file in your browser to test the updated search interface. The Todoist search results should update dynamically based on your selected facets.

## Contributing
If you'd like to contribute to this project, please fork the repository and submit a pull request with your changes. Ensure your code adheres to the existing style and conventions.

## License
This project is licensed under the Apache 2.0 License. See the LICENSE file for more information.
