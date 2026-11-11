# 2º SMR HTML EXAM (26-27)

Name: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Group: 


## Exercise 1. Lists and Text Formatting (2,5 points)

Write the HTML code needed to display the following information:


**Chemical Elements**

1. Metals
    - Iron
    - Copper
    - Aluminium
2. Non-metals
    - Oxygen
    - Carbon

After the list, add the following paragraph:

Chemical elements are classified according to their properties. Some of them, such as iron, are widely used in industry.

**Formatting requirements:**

- The text "Chemical Elements" at the beginning must be the main heading of the page.
- The words "chemical elements" in the paragraph must appear in bold.
- The word "properties" must appear in italics.
- The word "iron" must be highlighted in yellow, as if using a highlighter pen.

## Exercise 2. Lists (1,5 points)

Write the HTML code needed to display the following information:

<dl>
    <dt>CPU</dt>
    <dd>The main processor of the computer.</dd>
    <dt>RAM</dt>
    <dd>Temporary memory used while the computer is running.</dd>
    <dt>SSD</dt>
    <dd>A fast storage device that uses flash memory. </dd>
<dl>

<br><br><br><br><br><br><br>

## Exercise 3. Create an HTML Table (2,5 points)

Write the HTML code needed to create a table with the following information:

<table border="1">
    <caption>Festival program</caption>
    <thead>
        <tr>
            <th>Day</th>
            <th>Performance</th>
            <th>Time</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan="2">Friday</td>
            <td>Band A</td>
            <td>20:00</td>
        </tr>
        <tr>
            <td>Band B</td>
            <td>22:00</td>
        </tr>
        <tr>
            <td>Saturday</td>
            <td colspan="2">Break</td>
        </tr>
    </tbody>
</table>

**Requirements:**

- The table must include a specific section for the header row and another section for the rows containing the data.
- The first row must identify the columns using header cells.
- You must use the cell combinations shown in the example.

## Exercise 4. Image, Link and Text Formatting (3,5 points)

Write the HTML code needed to complete the following tasks:

- Display an image named mars.jpg, located in the `images` folder.
- The image must have the following alternative text: "Reddish surface of the planet Mars".
- The image must have a width of 300 pixels and a height of 400 pixels.
- When the image is clicked, the user must be redirected to `https://science.nasa.gov/mars/`.
- Below the image, display the text: "Mars is known as the Red Planet".
- Group the image and the text below it within the same element, indicating that the text is the image caption or description.

Next, add a paragraph containing the following text:

"The surface of Mars has an average temperature of -65°C and an area of 144,800,000 km². Its atmosphere contains CO₂ and its gravity is 38% of Earth's gravity."
