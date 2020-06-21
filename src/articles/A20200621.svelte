<script>
    import Article from '../reusables/Article.svelte';
</script>

<Article 
title="🎉 The Instrumentality Foundation launches version 1.0 of the Instrumentality Blog 🎉"
description="Come on in and see how we made the blog. What technologies did we use, what obstacles we faced and how we overcame them"
image="/assets/images/blog02.webp"
id="A20200621">

    <p>
        After a couple of days searching for a perfect way to create the Instrumentality blog and after going through numerous popular static site generators like
        Hugo and Jekyll, I am proud to announce that, as always, I went my own way and created a blog from scratch using Svelte.js and UIkit, and I created my own
        unique way of managing and uploading post to this blog.
    </p>

    <h2>
        Why I haven't used a static site generator?
    </h2>

    <p>
        While it may be true, that taking a ready-made theme and using markdown to write all the posts would have been a million times faster than my solution, I would 
        have sacrificed the freedom that creating my own thing offers me. Instrumentality is not about doing things the same way they have been done for years, it is
        about creating new things, changing workflows and experimenting with new ideas.
    </p>
    <p>
        Static site generators are great for people that want a quick solution and don't really want to dive into how everything works under the hood. They might change some
        colors or other elements of their theme of choice, but the heavy lifting was done before by somebody else. This is the first reason why I chose to build a blog from
        scratch, I wanted total control over every aspect of the blog and I wanted to be able to know how to tweak each element. Ready-made themes, since are not made by
        you, are hard to custmize since you don't know exactly how everything ties up.
    </p>
    <p>
        Another reason that weighed in my decision to not use something like <strong>Hugo</strong> or <strong>Jekyll</strong> is that they feel overly complicated to me.
        In a second I'll explain to you how this blog handles article posting, but there are a lot of rules in static site generators that one has to follow, like file naming
        conventions, snippets that the file must contain in order to be parsed correctly, etc. And in the end you are presented with an article written in Markdown which
        I feel like it's highly limiting for my taste. HTML on the other hand, is like Markdown on steroids, allowing me to really shape the articles on this blog in every
        way and form I like. Unlike the constrained environment of a static site generator, this blog can have posts that look totally different, from fonts to colors to animations and
        effects, those things are just impossible when using Markdown.
    </p>

    <h2>
        How I post articles on this blog
    </h2>
    <p>
        Posting is really simple on this blog and comes more naturally to me. The process lacks the automation that tools like Hugo and Jekyll have, but something similar will be
        implemented in the future so I'll be able to generate a new article with a simple terminal command. For now, though, I manually add a new article in the <code>/src/articles</code>
        folder. I usually name the files something like <code>A20200621.svelte</code> so that I make sure that every article has a unique name. In the future tool that I plan, the specified date will
        automatically be appended to your chosen name so you won't have to worry about uniqueness.
    </p>
    <p>
        This is a svelte component that must import the <code>Article.svelte</code> parent component and initialize it with some parameters like title, description, article image
        and an id which must be unique, therefore I'm using the file name again. Then, I'm just writing the article using the appropriate HTML tags. This article is later imported in the
        <code>ArticleList.svelte</code> component like so:

    </p>

        <pre>&lt;script&gt;
    import A20200621 from '../articles/A20200621.svelte';
&lt;/script&gt;</pre>

    <p>
        In the <code>ArticleList.svelte</code> component I just include the actual article inside <code>&lt;Lazy&gt;</code> tags and that's it. The article appears on the page.
    </p>

    <pre>&lt;section class="uk-section uk-flex uk-flex-column uk-flex-center"&gt;
    &lt;Lazy height=&lbrace;500&rbrace;&gt;
        &lt;A20200621 /&gt;
    &emsp&lt;/Lazy&gt;

&lt;/section&gt;</pre>

    <h2>
        Why Svelte.js and UIkit?
    </h2>

    <p>
        I went with Svelte for this project because it was marketed as being minimalist, fast and easy to use. I can say that it surely didn't disappoint in any of those areas,
        being one of the fastest frameworks I've ever seen. I paired it with UIkit because I have a lot of experience using it and for me it strikes the perfect balance between
        a minimal CSS framework and one full of features. 
    </p>

    <p>
        As a great example, I'll let here the code for creating the article cards. The card is a reusable svelte component that uses props and slots to fill the card with
        the actual article data. Think of this component as a template for all the articles in this blog. Each svelte component can has its own <code>&lt;script&gt;&lt;/script&gt;</code>
        tag and <code>&lt;style&gt;&lt;/style&gt;</code> tag. This allows for scoped logic and style for each component.
    </p>

        <pre>&lt;script&gt;
    export let image = "/assets/images/placeholder.jpg";
    export let title = "Placeholder title";
    export let description = "This is a placeholder description";
    export let id;
&lt;/script&gt;</pre>

    <p>
        The code you see above, can be found in <code>/src/reusables/Article.svelte</code> and describes the props of this component. It defines a set of variables
        that can be used when declaring an <strong>Article</strong> to specify certain things about the article, like title, image, etc.
    </p>

    <p>
        Since UIkit does a lot of stuff right the styling on this component is minimal, including mostly colors, fonts and different font sizes for the different
        ind of screens that are out there.
    </p>

    <pre>&lt;style&gt;
    .uk-card-media-top img &lbrace;
        object-fit: cover;
        width: 100%;
        height: 30vh;
    &rbrace;

    .uk-button &lbrace;
        color: #262229;
        font-family: 'Noto Sans', sans-serif;
        background: white;
        font-size: 1em;
        border: 1px solid #f3665b;
        transition: 0.3s all ease-in-out;
    &rbrace;

    .uk-button:hover &lbrace;
        background: #f3665b;
        color: white;
    &rbrace;

    h2.uk-modal-title &lbrace;
        font-family: 'Noto Sans', sans-serif;
        font-size: 1.2em;
        color: black;
    &rbrace;

    .uk-card-body p &lbrace;
        font-family: 'Noto Sans', sans-serif;
        font-size: 1em;
    &rbrace;

    /*On larger devices*/
    @media only screen and (min-width: 960px) &lbrace;
        .uk-card-media-top img &lbrace;
            height: 50vh;
        &rbrace;

        h2.uk-modal-title &lbrace;
            font-size: 2em;
        &rbrace;
    &rbrace;
&lt;/style&gt;</pre>

    <p>
        As you can see there's only pure CSS and vanilla JS so no fancy tricks are needed in order to use Svelte. After the javascript and style, next up we'll have a look
        at the HTML itself. Those are the building blocks that structure all the content in the way you see it when opening the blog. Most <code>.uk-*</code> classes are
        from UIkit and their names are pretty suggestive so it should be fairly easy to pick up what they're used for.
    </p>

    <pre>&lt;div id="article-card" class="uk-card uk-card-default uk-margin-bottom"&gt;

    &lt;div class="uk-card-media-top"&gt;
        &lt;!-- Card header --&gt;
        &lt;img src=&lbrace;image&rbrace; alt="A placeholder"&gt;
    &lt;/div&gt;

    &lt;div class="uk-card-body">
        &lt;h3 class="uk-card-title uk-text-center"&gt;&lbrace;title&rbrace;&lt;/h3&gt;
        &lt;p&gt;&lbrace;description&rbrace;...&lt;/p&gt;
        
        &lt;div class="uk-flex uk-flex-center"&gt;
            &lt;button class="uk-button" uk-toggle="target: #&lbrace;id&rbrace;" type="button">Read more&lt;/button&gt;
        &lt;/div&gt;

    &lt;/div&gt;

&lt;/div&gt;</pre>

    <p>
        You can see how props come into play now. Those variables are replaced at compile time by the values set for example in <code>A20200621</code> article, which is the
        one you're reading right now.

        The <code>Read more</code> button has a strange attribute <code>uk-toggle</code> which opens the modal you are in right now. A modal is a little window that, on this blog,
        hosts the actual article. Let's see how we can make a modal using the classes UIkit gives us.
    </p>

    <pre>&lt;div class="uk-modal-container" id=&lbrace;id&rbrace; uk-modal&gt;

    &lt;div class="uk-modal-dialog"&gt;

        &lt;div class="uk-modal-header"&gt;
            &lt;h2 class="uk-modal-title uk-text-center"&gt;&lbrace;title&rbrace;&lt;/h2&gt;
        &lt;/div&gt;

        &lt;div class="uk-modal-body" uk-overflow-auto&gt;
            &lt;button class="uk-modal-close-default" type="button" uk-close&gt;&lt;/button&gt;
            &lt;slot&gt;&lt;/slot&gt;
        &lt;/div&gt;
    &lt;/div&gt;

&lt;/div&gt;</pre>

    <p>
        The <code>&lt;slot&gt;</code> tag isn't a standard HTML tag, it comes with Svelte and when the whole source is compiled it will be replaced by the content you are reading now, which
        resides in <code>/scr/articles/A20200621.svelte</code>.
    </p>

    <hr class="uk-divider-icon">

    <p>
        I hope you found this knowledge interesting and I hope that if you take one thing from article is that you can create anything you want with any tool you choose and
        the choice of technologies has little impact in the end.
    </p>

</Article>