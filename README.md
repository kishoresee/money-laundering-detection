Dataset: [SAML-D](https://drive.google.com/file/d/1gzI1K-M35M6h1NFRbmpBOywlety38zuk/view?usp=drive_link)
$(document).ready(function () {
    $.ajax({
        url: _spPageContextInfo.webAbsoluteUrl + "/_api/web/lists/getbytitle('YourListName')/items",
        method: "GET",
        headers: {
            "Accept": "application/json;odata=verbose"
        },
        success: function (data) {
            var items = data.d.results;
            var output = "<ul>";
            items.forEach(function (item) {
                output += "<li>" + item.Title + "</li>";
            });
            output += "</ul>";
            $("#results").html(output);
        },
        error: function (error) {
            console.log("Error fetching data", error);
        }
    });
});
