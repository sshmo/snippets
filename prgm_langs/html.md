# html

* Add styles as a file

    ``` html
    <head>
        <link rel="stylesheet" href="./src/styles.css">
    </head>
    ```

* lists

    ```html
    <!-- ol: Ordered List -->
    <!-- ul: Unordered list -->
    <ol>
      <li>a</li>
      <li>b</li>
      <ul>
        <li>c</li>
        <li>d</li>
      </ul>
    </ol>
    ```

* many spaces!

    ```html
    <!-- use pre (preformatted) for many spaces! -->
    <pre> Hello                                 World!</pre>
    ```

* images

    ``` html
    <img src="./src/hello.png" alt="world!" width="600"/>
    ```

* links

    ``` html
    <a href="hello copy.html"> Click here </a>
    ```

* tables

    ```html
        <table>
        <thead>
            <tr>
            <th>heading1</th>
            <th>heading2</th>
            </tr>
        </thead>
        <tbody>
            <tr>
            <td>h1-data1</td>
            <td>h1-data2</td>
            </tr>
            <tr>
            <td>h2-data1</td>
            <td>h2-data2</td>
            </tr>
        </tbody>
        </table>
    ```

* forms

    ```html
    <form>
    <input type="text" placeholder="Full Name" name="fullname" />
    <input type="submit" />
    <input type="password" />
    <input type="radio" />
    <input list="dropdown" placeholder="maloo" />
    <datalist id="dropdown">
        <option>1</option>
        <option>2</option>
        <option>3</option>
        <option>4</option>
        <option>5</option>
        <option>6</option>
    </datalist>
    </form>
    ```
