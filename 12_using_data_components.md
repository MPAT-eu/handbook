# Data components

Some components fetch their data from elsewhere:

- the Data component fetches its content from a URL
- the DataFromStreamEvent takes its content from Stream Events

## Data component

The Data component has 3 parameters:

- the URL of the web service that provides the content
- the optional template to obtain the actual content from the fetched data
- the optional fetching period 

### Plain Data with URL

When only a URL is specified, the Data component behaves like a Text component. 
An AJAX call is made to the URL provided, and the fetched text is inserted as is
in the component. **The fetched text may be plain text or a URL fragment**.

### Using a fetching period

When a period is specified, the AJAX call is executed every period seconds, and the 
content of the component is updated.

### Using a template

When a template string is provided, the Data component assumes that **the fetched data 
is in the form of a JSON object**. 

The template string contains tags between {{ }} that are replaced with the value of the
tag property in the fetched data 
(in the manner of JS moustache or JS handlebars).

Example:

- template: 

| \<h1>{{title}}\</h1>\<hr/>\<p>{{para}}\</p> | 
|---|

- fetched data: 
<pre>
{
  "userId": 1,
  "title": "quod erat",
  "para": "qui ullam ratione quibusdam voluptatem quia omnis",
  "completed": false
}
</pre>
- resulting content: 

|\<h1>quod erat\</h1>\<hr/>\<p>qui ullam ratione quibusdam voluptatem quia omnis\</p></code>
|---|

- what is displayed:

| <h1>quod erat</h1><hr/><p>qui ullam ratione quibusdam voluptatem quia omnis</p> |
|---|


## DataFromStreamEvent component

The DataFromStreamEvent has 5 parameters:

- the Stream Event id
- the Stream Event name
- the Stream Event component tag
- the initial text
- the optional template to obtain the actual content from the event data

Id, name and tag of the Stream Event to listen to are HbbTV parameters.
If you do not know, the default values should be OK for you.
Otherwise, your broadcasting team will give you approriate values.

The initial text is the text that is displayed before any event is received.

The template is of the same type as the Data component.

### Plain event

Without template, the DataFromStreamEvent component behaves like a Text component. 
When receiving a Stream Event of matching parameters, the data from the event is 
extracted and placed into the component. **The event data may be plain text or a URL fragment**.

### Using a template

When a template string is provided, the DataFromStreamEvent component assumes 
that **the fetched data is in the form of a JSON object**. 

The template string contains tags between {{ }} that are replaced with the value of the
tag property in the fetched data 
(in the manner of JS moustache or JS handlebars).

Example:

- template: 

|\<h1>{{title}}\</h1>\<hr/>\<p>{{para}}\</p>|
|---|

- event data: 
<pre>
{
  "userId": 1,
  "title": "quod erat",
  "para": "qui ullam ratione quibusdam voluptatem quia omnis",
  "completed": false
}
</pre>
- resulting content: 

|\<h1>quod erat\</h1>\<hr/>\<p>qui ullam ratione quibusdam voluptatem quia omnis\</p>|
|---|

- what is displayed:

|<h1>quod erat</h1><hr/><p>qui ullam ratione quibusdam voluptatem quia omnis</p>|
|---|

