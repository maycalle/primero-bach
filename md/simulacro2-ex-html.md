# Practice Exam. A Visit to the Science Park

**File to create: `visit.html`**

The Science Park wants to publish a webpage to inform visitors about the activities available during its Open Day.

Write the HTML code needed to create the webpage using the following information and meeting all the requirements.

## 1. Page information

- The browser tab title must be **"Open Day – Science Park"**.
- Include a suitable meta description for search engines.

## 2. Page content

### Open Day

On May 15th, the Science Park is organising an Open Day to bring science and technology closer to the general public.

Admission is free, but some activities require prior registration. You can find more information on the [official Science Park website](https://www.parquecientifico.es/).

### Available activities

During the event, visitors will be able to take part in the following activities:

1. **Technology workshops**
   - Robotics:
     - Building a small robot.
     - Programming its movements.
   - 3D printing.
2. **Science experiments**
   - Chemistry experiments.
   - Observing chemical reactions.
3. **Astronomy**
   - Stargazing.
   - Identifying constellations.

### Activity schedule

<table border="1">
    <caption>Activity schedule</caption>
    <thead>
        <tr>
            <th>Day</th>
            <th>Activity</th>
            <th>Time</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan="3">Friday</td>
            <td>Robotics workshop</td>
            <td>10:00</td>
        </tr>
        <tr>
            <td>Chemistry experiments</td>
            <td>11:00</td>
        </tr>
        <tr>
            <td>Stargazing</td>
            <td>12:00</td>
        </tr>
        <tr>
            <td rowspan="2">Saturday</td>
            <td>3D printing</td>
            <td>10:30</td>
        </tr>
        <tr>
            <td>Children's activities</td>
            <td>12:00</td>
        </tr>
    </tbody>
</table>

The organisers recommend arriving at least 15 minutes before each activity starts.

### Useful information

- **Admission:** free.
- **Registration:** required for workshops.
- **Capacity:** limited.

### Scientific concepts

The event will include a small educational area where visitors can learn about some scientific concepts:

- **Energy:** the ability to cause changes or do work.
- **Matter:** anything that has mass and occupies space.
- **Atom:** the basic unit that makes up matter.

### Event image

Include an image called `park.jpg`, located in the `images` folder, showing a science park or a laboratory.

The image must:
- Have descriptive alternative text.
- Have a width of 400 pixels.
- Link to the official Science Park website.

## 3. Formatting and structure requirements

- Use different heading levels to organise the sections.
- Use paragraphs and lists with the appropriate HTML structure.
- Organise the activities using nested lists.
- Present the scientific concepts as a list of terms and definitions.
- The table must include a title and clearly distinguish the header row from the data rows.
- The **Friday** cell must extend across the three rows corresponding to that day.
- The **Saturday** cell must extend across the two rows corresponding to that day.
- Each activity must appear in a separate table row.
- Use appropriate semantic formatting to emphasise important information.
- Highlight the word **"free"** with a yellow background, as if using a highlighter.
- Display **"May 15th"** in bold.
- Place the image after the "Scientific concepts" section.