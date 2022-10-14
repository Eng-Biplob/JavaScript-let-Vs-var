<h1>JavaScript let Vs var</h1>
<p>In this tutorial, you will learn about the difference between let and var in JavaScript with the help of examples.</p>
<div>
    <div>
        <p>In JavaScript, both the keywords&nbsp;<code>var</code> and&nbsp;<code>let</code> are used to declare variables.</p>
        <p>The&nbsp;<code>let</code> keyword was introduced in the later version of JavaScript known as&nbsp;<strong>ES6(ES2015)</strong>. And it&apos;s the preferred way to declare variables.</p>
    </div>
</div>

<div>
    <div>
        <div>
            <h2>JavaScript let Vs var</h2>
            <p>Here&apos;s the overview of the differences between <code>let</code> and <code>var</code>.</p>
            <div>
                <table border="0">
                    <thead>
                        <tr>
                            <th>let</th>
                            <th>var</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>let is block-scoped.</td>
                            <td>var is function scoped.</td>
                        </tr>
                        <tr>
                            <td>let does not allow to redeclare variables.</td>
                            <td>var allows to redeclare variables.</td>
                        </tr>
                        <tr>
                            <td>Hoisting does not occur in let.</td>
                            <td>Hoisting occurs in var.</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            <hr>
            <h2>JavaScript let Vs var in Local Scope</h2>
            <h3>var is function scoped</h3>
            <p>The variable declared inside a function with <code>var</code> can be used anywhere within a function. For example,</p>
            <div>
                <div>
                    <div>
                        <div title="Click to copy"><br></div>
                        <pre><code>// program to print text
// variable a cannot be used here
function greet() {
    // variable a can be used here
    var a = &apos;hello&apos;;
    console.log(a);
}
// variable a cannot be used here

greet(); // hello</code></pre>
                    </div>
                </div>
                <div><a href="https://www.programiz.com/javascript/online-compiler" target="_blank">Run Code</a></div>
            </div>
            <p>In the above program, the variable <var>a</var> is declared with <code>var</code>. The variable <var>a</var> can be used anywhere inside the function <code>greet</code>.</p>
            <h3>let is block-scoped</h3>
            <p>The variable declared with <code>let</code> can only be accessed inside a block of code. For example,</p>
            <div>
                <div>
                    <div>
                        <div title="Click to copy"><br></div>
                        <pre><code>// program to print the text
// variable a cannot be used here
function greet() {
    let a = &apos;hello&apos;;

    // variable b cannot be used here
    if(a == &apos;hello&apos;){
        // variable b can be used here
        let b = &apos;world&apos;;
        console.log(a + &apos; &apos; + b);
    }

     // variable b cannot be used here
    console.log(a + &apos; &apos; + b); // error
}
// variable a cannot be used here

greet();</code></pre>
                    </div>
                </div>
                <div><a href="https://www.programiz.com/javascript/online-compiler" target="_blank">Run Code</a></div>
            </div>
            <p><strong>Output</strong></p>
            <pre><samp>hello world
Uncaught ReferenceError: b is not defined</samp></pre>
            <p>In the above program, the variable <var>a</var> is declared inside the function and it can be accessed anywhere inside the function (<var>a</var> becomes function scoped).</p>
            <p>However the variable <var>b</var> is declared inside the <code>if</code> block statement. <var>b</var> will be block-scoped and can only be accessed inside the <code>if</code> block.</p>
            <p>Hence when you try to access <var>b</var> outside of <code>if</code> block, an error occurs (as shown above in the program).</p>
            <p><strong>Note</strong>: The variables declared inside a function will be function scoped for both <code>var</code> and <code>let</code>.</p>
            <hr>
            <h2>let doesn&apos;t allow to redeclare Variables</h2>
            <p>1. A variable declared with <code>var</code> can be redeclared again. For example,</p>
            <div>
                <div>
                    <div>
                        <div title="Click to copy"><br></div>
                        <pre><code>var a = 5; // 5
var a = 3; // 3</code></pre>
                    </div>
                </div>
                <div><a href="https://www.programiz.com/javascript/online-compiler" target="_blank">Run Code</a></div>
            </div>
            <p>A variable declared with <code>let</code> cannot be redeclared within the same block or same scope. For example,</p>
            <div>
                <div>
                    <div>
                        <div title="Click to copy"><br></div>
                        <pre><code>let a = 5;
let a = 3; // error </code></pre>
                    </div>
                </div>
                <div><a href="https://www.programiz.com/javascript/online-compiler" target="_blank">Run Code</a></div>
            </div>
            <p><strong>Output</strong></p>
            <pre><samp>Uncaught SyntaxError: Identifier &apos;a&apos; has already been declared</samp></pre>
            <p>2. Redeclaring a variable with <code>var</code> in a different scope or block changes the value of the outer variable too. For example,</p>
            <div>
                <div>
                    <div>
                        <div title="Click to copy"><br></div>
                        <pre><code>var a = 5;
console.log(a); // 5
{
    var a = 3;
    console.log(a); // 3
}
console.log(a); // 3</code></pre>
                    </div>
                </div>
                <div><a href="https://www.programiz.com/javascript/online-compiler" target="_blank">Run Code</a></div>
            </div>
            <p><br></p>
            <div>
                <div>
                    <div>
                        <div><br></div>
                    </div>
                </div>
            </div>
            <div><br></div>
            <p>Redeclaring a variable with <code>let</code> in a different scope or block treats that variable as a different variable. And the value of a variable outside does not change. For example,</p>
            <div>
                <div>
                    <div>
                        <div title="Click to copy"><br></div>
                        <pre><code>let a = 5;
console.log(a); // 5
{
    let a = 3;
    console.log(a); // 3
}
console.log(a); // 5</code></pre>
                    </div>
                </div>
                <div><a href="https://www.programiz.com/javascript/online-compiler" target="_blank">Run Code</a></div>
            </div>
            <p>3. When a variable declared with <code>var</code> is used in a loop, the value of that variable changes. For example,</p>
            <div>
                <div>
                    <div>
                        <div title="Click to copy"><br></div>
                        <pre><code>var a = 2;
for(var a = 0; a &lt; 3; a++) {
    console.log(&apos;hello&apos;);
}
console.log(a); // 3</code></pre>
                    </div>
                </div>
                <div><a href="https://www.programiz.com/javascript/online-compiler" target="_blank">Run Code</a></div>
            </div>
            <p>In the above program, the <code>for</code> loop redeclares the variable <var>a</var>. Hence the value of <code>a</code> is changed to <strong>3</strong> at the end.</p>
            <p>When a variable declared with <strong>let</strong> is used in a loop, the value of a variable does not change. For example,</p>
            <div>
                <div>
                    <div>
                        <div title="Click to copy"><br></div>
                        <pre><code>let a = 2;
for(let a = 0; a &lt; 3; a++) {
    console.log(&apos;hello&apos;);
}
console.log(a); // 2</code></pre>
                    </div>
                </div>
                <div><a href="https://www.programiz.com/javascript/online-compiler" target="_blank">Run Code</a></div>
            </div>
            <p>In the above program, <code>for</code> loop treats variable <var>a</var> as a different variable than the one declared above. And the scope of that variable is only inside the <code>for</code> loop. Hence the value of variable <var>a</var> remains <strong>2</strong> at the end.</p>
            <hr>
            <h2>let Doesn&apos;t Allow Hoisting</h2>
            <p>The variables declared with <code>var</code> are hoisted to the top of the scope of the program. For example,</p>
            <div>
                <div>
                    <div>
                        <div title="Click to copy"><br></div>
                        <pre><code>console.log(a);
var a; // undefined (not an error)</code></pre>
                    </div>
                </div>
                <div><a href="https://www.programiz.com/javascript/online-compiler" target="_blank">Run Code</a></div>
            </div>
            <p>The keyword <code>let</code> does not allow hoisting. For example,</p>
            <div>
                <div>
                    <div>
                        <div title="Click to copy"><br></div>
                        <pre><code>console.log(a);
let a; // Uncaught ReferenceError: a is not defined</code></pre>
                    </div>
                </div>
                <div><a href="https://www.programiz.com/javascript/online-compiler" target="_blank">Run Code</a></div>
            </div>
            <p>If you want to learn more about hoisting, visit <a href="https://www.programiz.com/javascript/hoisting">JavaScript Hoisting</a>.</p>
            <hr>
            <h2>let and var Browser Support</h2>
            <p>Most of the modern browsers support the use of <code>let</code>. However, some browsers do not fully support <code>let</code>.</p>
            <p>To learn more, visit <a href="https://caniuse.com/#search=let">JavaScript let browser support</a>.</p>
            <hr>
            <div>
                <p><strong>Note</strong>: In case of global scope, both <code>var</code> and <code>let</code> will behave in the same way. For example,</p>
                <pre><code>var a = 5; // 5</code></pre>
                <p>The variable <var>a</var> will be global scoped and can be accessed anywhere in the program.</p>
                <pre><code>let a = 5; // 5</code></pre>
                <p>The variable <var>a</var> will be global scoped and can be accessed anywhere in the program.</p>
            </div>
        </div>
    </div>
    <div>
        <div>
            <div></div>
        </div>
    </div>
</div>
<div>
    <section>
        <div><br></div>
    </section>
</div>
<div>
    <div><br></div>
</div>
<p><br></p>
