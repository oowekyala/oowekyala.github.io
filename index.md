---
title: PMD Documentation website
keywords: java
permalink: index.html
toc: false
summary: >
    Welcome to PMD, an extensible cross-language static code analyzer.
    It finds common programming flaws like unused variables, empty catch blocks, unnecessary object creation,
    and so forth. Additionally it includes CPD, the copy-paste-detector. CPD finds duplicated code.
last_updated: August 2017
author: Jeff Jensen <jjensen@apache.org>, Andreas Dangel <andreas.dangel@adangel.org>
---


<!-- ## Welcome to PMD! -->

<!-- First time user? Then you may be interested in our [quickstart series](TODO)! -->

<br/>


{% unless site.output == "pdf" %}
<script src="js/jquery.shuffle.min.js"></script>
<script src="js/jquery.ba-throttle-debounce.min.js"></script>
{% endunless %}


<div class="row" >

{% include custom/knowledge_base_topic.html
           title="Getting started"
           datagroup="getting_started"
           image="fa-paper-plane"
           description="Get set-up and learn how to use PMD in a few simple steps."
%}

{% include custom/knowledge_base_topic.html
           title="User documentation"
           datagroup="userdocs"
           image="fa-cogs"
           description="Topics to learn how to use PMD, and rule references."
%}

{% include custom/knowledge_base_topic.html
           title="Writing rules"
           datagroup="extending"
           image="fa-edit"
           description="Writing your own rules allows you to adapt PMD to your most specific needs."
%}

{% include custom/knowledge_base_topic.html
           title="Contributing"
           datagroup="contributing"
           image="fa-github"
           description="You can contribute to PMD really easily lol."
%}

<!-- sizer -->
<div class="col-xs-6 col-sm-4 col-md-1 shuffle_sizer"></div>

</div>





<div class="col-lg-12">
     <h2 class="page-header" id='grid-rule'/>
</div>


<div class="filter-options">
      <button class="btn btn-primary" data-group="all">All</button>
      <button class="btn btn-primary" data-group="getting_started">Getting Started</button>
      <button class="btn btn-primary" data-group="userdocs">User documentation</button>
      <button class="btn btn-primary" data-group="extending">Extending PMD</button>
      <button class="btn btn-primary" data-group="contributing">Contributing</button>
</div>




<div id="grid" class="row">

    {% include custom/shuffle_panel.html
       tags="getting_started"
       datagroups='["getting_started"]'
       description="These pages summarize the gist of PMD usage to get you started quickly."
       title="Getting started" %}


    {% include custom/shuffle_panel.html
       tags="rule_references"
       datagroups='["userdocs"]'
       title="Rule references"
       description="Pick your language to find out about the rule it supports."
       image="fa-database"
       titlemaker="page.language_name" %}

    {% include custom/shuffle_panel.html
       tags="userdocs,extending"
       datagroups='["userdocs", "extending", "contributing"]'
       title="Writing rules"
       description="These pages document the process of writing and testing custom rules and metrics for PMD."
    %}

    {% include custom/shuffle_panel.html
       tags="userdocs"
       except_tags="extending,tools"
       datagroups='["userdocs"]'
       image="fa-cog"
       title="Usage and configuration"
       description="Learn how to build effective and versatile rulesets."
    %}


    {% include custom/shuffle_panel.html
       tags="devdocs"
       except_tags="extending"
       datagroups='["contributing"]'
       image="fa-github"
       title="Contributing"
       description="If you'd like to help us build PMD, these topics may interest you. See you around!"
    %}



    {% include custom/shuffle_panel.html
       tags="tools"
       datagroups='["userdocs"]'
       title="Tools and integrations"
       description="These pages describe solutions that integrate PMD within your build process."
    %}

    {% include custom/shuffle_panel.html
       tags="devdocs,extending"
       datagroups='["contributing","extending"]'
       title="Major contributions"
       description=""
    %}


</div>

<!-- {% include image.html file="pmd-logo-big.png" alt="PMD Logo" %} -->

{% unless site.output == "pdf" %}

{% include initialize_shuffle.html %}

{% endunless %}



{% include links.html %}