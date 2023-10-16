
<h1 class="code-line" data-line-start=0 data-line-end=1 ><a id="AqueelEcomExpert_0"></a>Aqueel-Ecom-Expert</h1>
<p class="has-line-data" data-line-start="2" data-line-end="3"><img src="https://ecomexperts.io/cdn/shop/files/image_26.png?v=1684157387&amp;width=220" alt="N|Solid"></p>
<ul>
<li class="has-line-data" data-line-start="3" data-line-end="4">Shopify</li>
<li class="has-line-data" data-line-start="4" data-line-end="5">Theme customization</li>
<li class="has-line-data" data-line-start="5" data-line-end="7">✨Liquid</li>
</ul>
<h2 class="code-line" data-line-start=7 data-line-end=8 ><a id="Task_CheckList__7"></a>Task CheckList ✔️</h2>
<ul>
<li class="has-line-data" data-line-start="9" data-line-end="10">Change the name of the product “Black Leather Bag” to “Handbag” - ✅</li>
<li class="has-line-data" data-line-start="10" data-line-end="11">Add 3 variants to the product: “Black” - “Red” - “Tan” - ✅</li>
<li class="has-line-data" data-line-start="11" data-line-end="12">Add the price of each variant respectively 20$ black - 9.99$ red - 1115.01$ tan - ✅</li>
<li class="has-line-data" data-line-start="12" data-line-end="13">Modify the code to ensure when a site visitor clicks on Black variant - only images of the black handbag show. If the user selects red- only red handbags show and so on. ( Please do Swatches ) - ✅</li>
<li class="has-line-data" data-line-start="13" data-line-end="14">Add the variant options “Unselected” ,“Small”, “Medium”, “Large” - as a DROPDOWN option - ✅</li>
<li class="has-line-data" data-line-start="14" data-line-end="15">Make sure that when the page is refreshed while the size selected is either small, medium or large - the size variant will be unselected after the page is refreshed. - ✅</li>
<li class="has-line-data" data-line-start="15" data-line-end="16">Find “Soft Winter Jacket” and make sure visitors can not find/buy this product as this product will only be offered in a bundle format - ✅</li>
<li class="has-line-data" data-line-start="16" data-line-end="17">When the “Leather Bag” -with variant options “Black” &amp; “Medium ” is added to the cart. The “Soft Winter Jacket” product will also be automatically added to the cart for an additional price of 0.01$ - ✅</li>
<li class="has-line-data" data-line-start="17" data-line-end="19">If “Leather Bag (black, medium )” is removed from the cart make sure “soft winter Jacket” is also automatically removed along with the leather bag ( black, medium). - ✅</li>
</ul>
<h2 class="code-line" data-line-start=19 data-line-end=20 ><a id="Tech_19"></a>Tech</h2>
<ul>
<li class="has-line-data" data-line-start="22" data-line-end="23">[Shopify Docs] -  for web Refrence!</li>
<li class="has-line-data" data-line-start="23" data-line-end="24">[VS code Editor] - Code Editor for Liquid</li>
</ul>
<h2 class="code-line" data-line-start=27 data-line-end=28 ><a id="Installation_27"></a>Installation</h2>
<p class="has-line-data" data-line-start="29" data-line-end="30"><a href="https://nodejs.org/">Node.js</a> v16+ , Ruby on Rails , Shopify CLI</p>
<h2 class="code-line" data-line-start=32 data-line-end=33 ><a id="Development_32"></a>Development</h2>
<p class="has-line-data" data-line-start="33" data-line-end="34">This section contains all logic and Development steps and my approach toward…</p>
<ol>
<li class="has-line-data" data-line-start="35" data-line-end="37">Change the name of the product “Black Leather Bag” to “Handbag”</li>
</ol>
<pre><code class="has-line-data" data-line-start="38" data-line-end="40" class="language-sh">-- Login to store &gt;  Products &gt;[changed name of Product]
</code></pre>
<ol start="2">
<li class="has-line-data" data-line-start="40" data-line-end="41">Add 3 variants to the product: “Black” - “Red” - “Tan”</li>
</ol>
<pre><code class="has-line-data" data-line-start="42" data-line-end="44" class="language-sh">-- Login to store &gt;  Products &gt; Add variants of Products (size ,color etc)
</code></pre>
<ol start="3">
<li class="has-line-data" data-line-start="44" data-line-end="46">Add the price of each variant respectively 20$ black - 9.99$ red - 1115.01$ tan</li>
</ol>
<pre><code class="has-line-data" data-line-start="47" data-line-end="49" class="language-sh">-- Login to store &gt;  Products &gt; Add variants of Products (size ,color etc)
</code></pre>
<ol start="4">
<li class="has-line-data" data-line-start="49" data-line-end="51">Modify the code to ensure when a site visitor clicks on Black variant - only images of the black handbag show. If the user selects red- only red handbags show and so on. ( Please do Swatches )</li>
</ol>
<p class="has-line-data" data-line-start="51" data-line-end="52">I have added Variants from product page and for swatches I have done written below for</p>
<pre><code class="has-line-data" data-line-start="53" data-line-end="63" class="language-sh">{% <span class="hljs-keyword">if</span> product.variants[forloop.index0].image != blank %}
    &lt;label <span class="hljs-keyword">for</span>=<span class="hljs-string">"{{ section.id }}-{{ option.position }}-{{ forloop.index0 }}"</span> style=<span class="hljs-string">"background-image:url({{ product.variants[forloop.index0].image | img_url:"</span><span class="hljs-string">"  }})"</span>&gt;
    &lt;/label&gt;
      {% <span class="hljs-keyword">else</span> %}
     &lt;label <span class="hljs-keyword">for</span>=<span class="hljs-string">"{{ section.id }}-{{ option.position }}-{{ forloop.index0 }}"</span>&gt;
      {{ value -}}
      &lt;span class=<span class="hljs-string">"visually-hidden"</span>&gt;{{ <span class="hljs-string">'products.product.variant_sold_out_or_unavailable'</span> | t }}&lt;/span&gt;
    &lt;/label&gt;
    {% endif %}
</code></pre>
<ol start="5">
<li class="has-line-data" data-line-start="63" data-line-end="65">Add the variant options “Unselected” ,“Small”, “Medium”, “Large” - as a DROPDOWN option</li>
</ol>
<p class="has-line-data" data-line-start="65" data-line-end="66">Written a custom Liquid code added as a snippet and Placed it below variant block</p>
<pre><code class="has-line-data" data-line-start="67" data-line-end="74" class="language-sh">&lt;select id=<span class="hljs-string">"size"</span>&gt;
  &lt;option value=<span class="hljs-number">0</span> selected&gt;Unselected&lt;/option&gt;
  &lt;option value=<span class="hljs-string">"small"</span>&gt;Small&lt;/option&gt;
  &lt;option value=<span class="hljs-string">"medium"</span>&gt;Medium&lt;/option&gt;
  &lt;option value=<span class="hljs-string">"large"</span>&gt;Large&lt;/option&gt;
&lt;/select&gt;
</code></pre>
<ol start="6">
<li class="has-line-data" data-line-start="74" data-line-end="76">Make sure that when the page is refreshed while the size selected is either small, medium or large - the size variant will be unselected after the page is refreshed.</li>
</ol>
<p class="has-line-data" data-line-start="76" data-line-end="77">I achived this using this js Script</p>
<pre><code class="has-line-data" data-line-start="78" data-line-end="88" class="language-sh">&lt;script&gt;
  document.addEventListener(<span class="hljs-string">"DOMContentLoaded"</span>, <span class="hljs-function"><span class="hljs-title">function</span></span> () {
    const sizeDropdown = document.getElementById(<span class="hljs-string">"Size"</span>);
    const selectedSize = <span class="hljs-built_in">local</span>Storage.getItem(<span class="hljs-string">"selectedSize"</span>);
    <span class="hljs-keyword">if</span> (selectedSize &amp;&amp; selectedSize !== <span class="hljs-string">"Unselected"</span>) {
      sizeDropdown.value = selectedSize;
    }
  });
&lt;/script&gt;
</code></pre>
<ol start="7">
<li class="has-line-data" data-line-start="88" data-line-end="89">Find “Soft Winter Jacket” and make sure visitors can not find/buy this product as this product will only be offered in a bundle format</li>
</ol>
<pre><code class="has-line-data" data-line-start="90" data-line-end="92" class="language-sh">created a metaField of Integer and made seo disabled 
</code></pre>
<ol start="8">
<li class="has-line-data" data-line-start="92" data-line-end="94">When the “Leather Bag” -with variant options “Black” &amp;  is added to the cart. The “Soft Winter Jacket” product will also be automatically added to the cart for an additional price of 0.01$</li>
</ol>
<p class="has-line-data" data-line-start="94" data-line-end="95">Approach to be Taken</p>
<pre><code class="has-line-data" data-line-start="96" data-line-end="99" class="language-sh"> Used app CartBot for adding free item to cart and vise versa <span class="hljs-built_in">where</span> you can add Automatic Discount <span class="hljs-keyword">if</span> user selects X product automatically Y product will be added to inventory and vice versa

</code></pre>
<p class="has-line-data" data-line-start="99" data-line-end="100">We can use Apps for Discount but it will <strong>Reduce the Speed of our App</strong>.</p>
