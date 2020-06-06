<template>
  <div>
    <div class="b-content" v-html="content">

    </div>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        content: '<p>According to people in the know, React Hooks are hot, hot, hot. In this article, we follow Christian Jensen&#39;s&nbsp;<a href="https://scrimba.com/g/greacthooks?utm_source=dev.to&amp;utm_medium=referral&amp;utm_campaign=greacthooks_launch_article">14-part tutorial</a>&nbsp;to find out about the basics of this new feature of React. Follow along to find out more!</p>\n' +
          '\n' +
          '<p><img alt="React Hooks we will learn in this course" src="https://thepracticaldev.s3.amazonaws.com/i/mh1hdo0zzhtgei8gv614.png" /></p>\n' +
          '\n' +
          '<h1>Intro</h1>\n' +
          '\n' +
          '<p><img alt="Paint app we will build during this project" src="https://thepracticaldev.s3.amazonaws.com/i/1j9osq1fshioocmoo0v4.png" /></p>\n' +
          '\n' +
          '<p>Hooks are new to the React library and allow us to share logic between components and make them reusable.</p>\n' +
          '\n' +
          '<p>In this course, we will be building a paint app similar to Microsoft Paint, which will allow us to name our project, switch out colors, get a new batch of colors and of course paint.</p>\n' +
          '\n' +
          '<p>Scrimba allows you to pause screencasts at any time and play with the code. It&#39;s a great way to learn by doing!</p>\n' +
          '\n' +
          '<h1>Prerequisites</h1>\n' +
          '\n' +
          '<p>The course assumes some&nbsp;<a href="https://www.freecodecamp.org/news/learn-modern-javascript-in-this-free-28-part-course-7ec8d353eb/">prior knowledge of ES6</a>,&nbsp;<a href="https://www.freecodecamp.org/news/learn-react-js-in-5-minutes-526472d292f4/">JSX, State and Props</a>, but no worries, we&#39;ve got you covered - check out our Scrimba articles by hitting the links above.</p>\n' +
          '\n' +
          '<p>If you are completely new to React, be sure to check out our&nbsp;<a href="https://scrimba.com/g/glearnreact?utm_source=dev.to&amp;utm_medium=referral&amp;utm_campaign=greacthooks_launch_article">Scrimba React course</a></p>\n' +
          '\n' +
          '<h1><code>useState</code>&nbsp;- Part 1</h1>\n' +
          '\n' +
          '<p>First, we give our application a way to manage state using useState.</p>\n' +
          '\n' +
          '<p>In our&nbsp;<code>&lt;Playground.js /&gt;</code>&nbsp;component, we declare a component called&nbsp;<code>&lt;Playground /&gt;</code>&nbsp;and create buttons to increment and decrement it. We then give useState an argument of (0) and use state restructuring to get&nbsp;<code>state</code>&nbsp;and&nbsp;<code>setState</code>&nbsp;(the function which updates the state) from our&nbsp;<code>useState</code>&nbsp;function. These are now renamed to&nbsp;<code>count</code>&nbsp;and&nbsp;<code>setCount</code>. We then render our count in the browser.</p>\n' +
          '\n' +
          '<p>Lastly, we render buttons which update the count using an inline function which will be triggered on the click.</p>\n' +
          '\n' +
          '<p><img alt="Incrementing count with our buttons" src="https://thepracticaldev.s3.amazonaws.com/i/kohiz9hz2f49n5i80l71.png" /></p>\n' +
          '\n' +
          '<p>To ensure our count is accurate, we pass a function to our&nbsp;<code>setState</code>&nbsp;function instead of a value. This function takes the current state as its argument, which is then updated:</p>\n' +
          '\n' +
          '<pre>\n' +
          '<code>import React, { useState } from &quot;react&quot;;\n' +
          'import randomColor from &quot;randomcolor&quot;;\n' +
          '\n' +
          'export default function Playground() {\n' +
          '\tconst [count, setCount] = useState(0);\n' +
          '\treturn (\n' +
          '\t\t&lt;div&gt;\n' +
          '\t\t\t{count}\n' +
          '\t\t\t&lt;button onClick={() =&gt; setCount((currentCount) =&gt; currentCount - 1)}&gt;\n' +
          '\t\t\t\t-\n' +
          '\t\t\t&lt;/button&gt;\n' +
          '\t\t\t&lt;button onClick={() =&gt; setCount((currentCount) =&gt; currentCount + 1)}&gt;\n' +
          '\t\t\t\t+\n' +
          '\t\t\t&lt;/button&gt;\n' +
          '\t\t&lt;/div&gt;\n' +
          '\t);\n' +
          '}\n' +
          '</code></pre>\n' +
          '\n' +
          '<p>If you&#39;re worried about the performance of inline functions, take a look a&nbsp;<a href="https://cdb.reacttraining.com/react-inline-functions-and-performance-bdff784f5578">this</a>&nbsp;blog.</p>\n' +
          '\n' +
          '<h1><code>useState</code>&nbsp;- Part 2</h1>\n' +
          '\n' +
          '<p>Now we add our name input to the&nbsp;<code>&lt;Name.js /&gt;</code>&nbsp;component so the user can name their project.</p>\n' +
          '\n' +
          '<p>To set up<code>&lt;Name.js /&gt;</code>&nbsp;with a&nbsp;<code>useState</code>&nbsp;Hook, we need to import the Hook with a named import and then set our state up. Our state will be&nbsp;<code>name</code>&nbsp;and we will update it with setName. We then call useState and pass in an empty string as our default state value.</p>\n' +
          '\n' +
          '<p>We now need an input element with four properties. These are:</p>\n' +
          '\n' +
          '<ul>\n' +
          '\t<li><code>value</code>, which will always be the state&nbsp;<code>name</code>&nbsp;from above</li>\n' +
          '\t<li><code>onChange</code>, which will use&nbsp;<code>setState</code>&nbsp;inline to update&nbsp;<code>name</code>&nbsp;by passing the value into setState</li>\n' +
          '\t<li><code>onClick</code>&nbsp;which uses setSelectionRange which takes a start index of 0 and end index of the length of the string to select the entire name, making it easier for the end-user to change the name.</li>\n' +
          '\t<li><code>placeholder</code>, which we set to &#39;Untitled&#39;.</li>\n' +
          '</ul>\n' +
          '\n' +
          '<pre>\n' +
          '<code>import React, { useState } from &quot;react&quot;;\n' +
          '\n' +
          'export default function Name() {\n' +
          '\tconst [name, setName] = useState(&quot;&quot;);\n' +
          '\treturn (\n' +
          '\t\t&lt;label className=&quot;header-name&quot;&gt;\n' +
          '\t\t\t&lt;input\n' +
          '\t\t\t\tvalue={name}\n' +
          '\t\t\t\tonChange={(e) =&gt; setName(e.target.value)}\n' +
          '\t\t\t\tonClick={(e) =&gt; e.target.setSelectionRange(0, e.target.value.length)}\n' +
          '\t\t\t\tplaceholder=&quot;Untitled&quot;\n' +
          '\t\t\t/&gt;\n' +
          '\t\t&lt;/label&gt;\n' +
          '\t);\n' +
          '}\n' +
          '</code></pre>\n' +
          '\n' +
          '<p>We can now name our project and select the name to reset it with just one click:</p>\n' +
          '\n' +
          '<p><img alt="Project\'s name input in action." src="https://thepracticaldev.s3.amazonaws.com/i/rgupvtuwliarlt2woyrj.png" /></p>\n' +
          '\n' +
          '<h1><code>useEffect</code></h1>\n' +
          '\n' +
          '<p>Currently, our Playground.js component is simply rendering a counter where can increment or decrement the count. Now we will update this so that every time the count is changed, the color of something is also changed.</p>\n' +
          '\n' +
          '<p>We use the useState Hook to set up the initial color, which we set to&nbsp;<code>null</code>&nbsp;and the function to update it (<code>setColor</code>). Now, we set up&nbsp;<code>useEffect</code>&nbsp;to update this color.&nbsp;<code>useEffect</code>&#39;s first argument is setColor, which we want to set to a&nbsp;<code>randomColor</code>.</p>\n' +
          '\n' +
          '<p>As we only want a change in&nbsp;<code>count</code>&nbsp;to trigger&nbsp;<code>useEffect</code>, we set this as the second argument. If the count value hasn&#39;t changed, the Hook will not run the effect and the color will remain the same.</p>\n' +
          '\n' +
          '<pre>\n' +
          '<code>import React, { useState, useEffect } from &quot;react&quot;;\n' +
          'import randomColor from &quot;randomcolor&quot;;\n' +
          '\n' +
          'export default function Playground() {\n' +
          '\tconst [count, setCount] = useState(0);\n' +
          '\n' +
          '\tconst [color, setColor] = useState(null);\n' +
          '\tuseEffect(() =&gt; {\n' +
          '\t\tsetColor(randomColor());\n' +
          '\t}, [count]);\n' +
          '\n' +
          '\treturn (\n' +
          '\t\t&lt;div style={{ borderTop: `10px solid ${color}` }}&gt;\n' +
          '\t\t\t{count}\n' +
          '\t\t\t&lt;button onClick={() =&gt; setCount((currentCount) =&gt; currentCount - 1)}&gt;\n' +
          '\t\t\t\t-\n' +
          '\t\t\t&lt;/button&gt;\n' +
          '\t\t\t&lt;button onClick={() =&gt; setCount((currentCount) =&gt; currentCount + 1)}&gt;\n' +
          '\t\t\t\t+\n' +
          '\t\t\t&lt;/button&gt;\n' +
          '\t\t&lt;/div&gt;\n' +
          '\t);\n' +
          '}\n' +
          '</code></pre>\n' +
          '\n' +
          '<p>Now, our color changes every time we increment or decrement our count.</p>\n' +
          '\n' +
          '<p><img alt="initial color" src="https://thepracticaldev.s3.amazonaws.com/i/6b6n7h96pkk89llw6abi.png" /></p>\n' +
          '\n' +
          '<p><img alt="color changed by one increment" src="https://thepracticaldev.s3.amazonaws.com/i/vawilltd0p7mu15lwa1d.png" /></p>\n' +
          '\n' +
          '<p><img alt="color changed by a second increment" src="https://thepracticaldev.s3.amazonaws.com/i/sq1ouu7f3d7u26kuov3f.png" /></p>\n' +
          '\n' +
          '<p><img alt="color changed by one decrement" src="https://thepracticaldev.s3.amazonaws.com/i/f2paopu37b35ojior8s7.png" /></p>\n' +
          '\n' +
          '<h1><code>useState</code>&nbsp;&amp;&nbsp;<code>useEffect</code>&nbsp;Challenge</h1>\n' +
          '\n' +
          '<p>It&#39;s now time to test the skills we have acquired so far. In this screencast, a function which gets some random colors for us has been added to &lt;Paint.js /&gt;:</p>\n' +
          '\n' +
          '<pre>\n' +
          '<code>const getColors = () =&gt; {\n' +
          '\tconst baseColor = randomColor().slice(1);\n' +
          '\tfetch(`https://www.thecolorapi.com/scheme?hex=${baseColor}&amp;mode=monochrome`)\n' +
          '\t\t.then((res) =&gt; res.json())\n' +
          '\t\t.then((res) =&gt; {\n' +
          '\t\t\tsetColors(res.colors.map((color) =&gt; color.hex.value));\n' +
          '\t\t\tsetActiveColor(res.colors[0].hex.value);\n' +
          '\t\t});\n' +
          '};\n' +
          '</code></pre>\n' +
          '\n' +
          '<p>Our task is to write the functions for&nbsp;<code>setColors</code>, which will give us an array of hex colors and&nbsp;<code>setActiveColor</code>, which will tell use what the active color is.</p>\n' +
          '\n' +
          '<p>If we set up everything correctly, the UI will update with five colors which we can click on to expand. We only need useState and useEffect for this test.</p>\n' +
          '\n' +
          '<h1><code>useState</code>&nbsp;&amp;&nbsp;<code>useEffect</code>&nbsp;Solution#</h1>\n' +
          '\n' +
          '<p>In&nbsp;<a href="https://scrimba.com/p/pKkkVU3/cDbkNJsg?utm_source=dev.to&amp;utm_medium=referral&amp;utm_campaign=greacthooks_launch_article">this</a>&nbsp;screencast, Christian walks us through how to give functionality to the&nbsp;<code>&lt;ColorPicker /&gt;</code>&nbsp;component. At the end of it, we now have some colors:</p>\n' +
          '\n' +
          '<p><img alt="colors visible in UI" src="https://thepracticaldev.s3.amazonaws.com/i/rxe2h70fqoldqf6ouoss.png" /></p>\n' +
          '\n' +
          '<h1><code>useEffect</code>&nbsp;Clean Up</h1>\n' +
          '\n' +
          '<p>Now we add a component called&nbsp;<code>&lt;WindowSize.js /&gt;</code>&nbsp;which will show the window width and height at the bottom of the screen when the user resizes the window. This then disappears after half a second.</p>\n' +
          '\n' +
          '<p>When we set up a timer or an event listener, we also need to clean it up once the component unmounts. This requires two pieces of state - the window size and visibility of the&nbsp;<code>&lt;WindowSize /&gt;</code>&nbsp;component:</p>\n' +
          '\n' +
          '<pre>\n' +
          '<code>export default function WindowSize() {\n' +
          '\tconst [[windowWidth, windowHeight], setWindowSize] = useState([\n' +
          '\t\twindow.innerWidth,\n' +
          '\t\twindow.innerHeight,\n' +
          '\t]);\n' +
          '\tconst [visible, setVisible] = useState(false);\n' +
          '}\n' +
          '</code></pre>\n' +
          '\n' +
          '<p>Now we set up our effect, which adds the event listener:</p>\n' +
          '\n' +
          '<pre>\n' +
          '<code>useEffect(() =&gt; {\n' +
          '\tconst handleResize = () =&gt; {};\n' +
          '\twindow.addEventListener(&quot;resize&quot;, handleResize);\n' +
          '});\n' +
          '</code></pre>\n' +
          '\n' +
          '<p>Next, we set up the cleanup phase. This returns the function and an empty array is passed in to tell it that useEffect should only run on the first mount. The cleanup will then run and remove the event listener:</p>\n' +
          '\n' +
          '<pre>\n' +
          '<code>useEffect(() =&gt; {\n' +
          '\tconst handleResize = () =&gt; {};\n' +
          '\twindow.addEventListener(&quot;resize&quot;, handleResize);\n' +
          '\treturn () =&gt; window.removeEventListener(&quot;resize&quot;, handleResize);\n' +
          '}, []);\n' +
          '</code></pre>\n' +
          '\n' +
          '<p>We now set up the window size, the visibility and the timer so that the the resize window appears and then disappears after 500 milliseconds:</p>\n' +
          '\n' +
          '<pre>\n' +
          '<code>const [visible, setVisible] = useState(false);\n' +
          'useEffect(() =&gt; {\n' +
          '\tconst handleResize = () =&gt; {\n' +
          '\t\tsetWindowSize([window.innerWidth, window.innerHeight]);\n' +
          '\t\tsetVisible(true);\n' +
          '\t\tsetTimeout(() =&gt; setVisible(false), 500);\n' +
          '\t};\n' +
          '\twindow.addEventListener(&quot;resize&quot;, handleResize);\n' +
          '\treturn () =&gt; window.removeEventListener(&quot;resize&quot;, handleResize);\n' +
          '}, []);\n' +
          '</code></pre>\n' +
          '\n' +
          '<p>However, we do not want to add a new timer every time the user resizes the window, so we also need to clean up the timer with&nbsp;<code>clearTimeout(timeoutId)</code>:</p>\n' +
          '\n' +
          '<pre>\n' +
          '<code>timeoutId = setTimeout(() =&gt; setVisible(false), 500);\n' +
          '</code></pre>\n' +
          '\n' +
          '<p>To give&nbsp;<code>clearTimeout</code>&nbsp;the&nbsp;<code>timeoutId</code>&nbsp;from the last time the function ran, we use&nbsp;<em>closures</em>, which means that we declare our&nbsp;<code>timeoutId</code>&nbsp;variable outside the&nbsp;<code>handleResize</code>&nbsp;function. This way, the variable is still available to the inner function. Every time the function runs, the previous timeout will be cleared and a new one will be set up.</p>\n' +
          '\n' +
          '<p>Lastly, we render our resize function to the browser.The final code can be seen in the screencast.</p>\n' +
          '\n' +
          '<p>Now, whenever the user resizes their window, the window size is set to the current window size, the visibility is set to true, and a timer is started to set the visibility to false after 500 milliseconds.</p>\n'
      }
    }
  }
</script>

<style scoped lang="scss">
  .b-content {
    font-size: 17px !important;
    p {
      img {
        text-align: center;
      }
    }
  }
</style>
