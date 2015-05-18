Kod hbs pojedyńczego posta z wykorzystaniem dostępnych tagów

{{#with post}}


    <div class="row">
        <div class="col-xs-12">
            <ol class="breadcrumb small">
            
                <li>
                    <a href="{{../forum_path}}">{{../forum_name}}</a>
                </li>

                {{#if category}}
                <li>
                    <a href="{{category.url}}">{{category.name}}</a>
                </li>
                {{/if}}

                <li class="active">{{title}}</li>

            </ol>


        </div>
        <!-- col-sm-12 -->
    </div>
    <!-- row -->


    <div class="row posts_comments one_post">

        <div class="col-xs-2 text-muted">
            
            <div class="text-center votes_vote">

            {{{vote_box}}}

            </div> <!-- votes_vote -->

        </div> <!-- col-sm-2 -->


        <div class="col-xs-10 single_post">
            <div class="panel panel-default post_details">
                <div class="panel-body">


                    {{#each attachments}}
                        {{#if image}}

                            <div class="post_image_place text-center">
                                <img src="{{url_medium}}" alt="{{file_name}} {{url}}" />
                            </div>
                            <!-- post_image_place -->              

                        {{/if}}
                    {{/each}}                



                    <div class="title_and_marks">
                        <h3>

                            {{title}}

                            <span class="badge {{kind}}" title="Oznaczone jako: {{kind}}">{{kind}}</span> 
                            <span class="label label-default icon_mark new" style="" title="Ma status: nowe">!! nowe</span>

                        </h3>
                    </div>
                    <!-- title_and_marks -->


                    <div class="post_content">
   

                        <p>
                            {{{content}}}
                        </p>   


                        <div class="clear"></div>

                        {{#if attachments}}


                            <div class="attachment_list">

                                <ul class="list-group list-group-sm panel-default">

                                    <li class="list-group-item active panel-heading">
                                        <i class="glyphicon glyphicon-link"></i> 
                                            Załączniki
                                        </li>


                                        {{#each attachments}}
                                            {{#if image}}

                                               <li class="list-group-item">
                                                    <a href="{{url}}" target="_blank">{{file_name}}</a>
                                                </li>           

                                            {{/if}}
                                        {{/each}}  
     
                                </ul>

                            </div>  <!-- attachment_list -->

                            <div class="clear"> </div>

                        {{/if}}                         

                    </div>
                    <!-- post_content -->

                    <div class="well well-sm small">




                        {{#if user}}


                            <a class="show_user" href="{{user.profile_path}}">
                                <img width="40" height="40" title="{{user.login}} {{user.first_name}} {{user.last_name}}" alt="{{user.login}} " src="{{user.avatar}} ">
                            </a>                                



                        {{else}}

                           <span style="text-decoration: underline">anonim</span> 

                        {{/if}}


       
                        <span class="show_date _timeago" title="{{creaed_at}}"> {{creaed_at}}</span>

                        <div class="pull-right">
                          <!--fb like -->
                        </div>

                    </div> <!-- well well-sm -->
                    

                    <a class="spam_report btn btn-default btn-xs" data-method="post" data-remote="true" href="#" title="Zgłoś naruszenie zasad">

                        !! Zgłoś naruszenie zasad

                    </a> 

                </div> <!-- panel-body -->

            </div> <!-- panel post_details -->





            <div id="who_voted" class="panel panel-default"> 

                <div class="panel-body">




                    Głosów <b> {{votes_count}}</b>:

                    {{#each voters}}

                        <span class="label label-primary">

                            <a href="{{user.profile_path}}">
                                <img title="{{user.login}}" alt="{{user.login}}" src="http://s3-eu-west-1.amazonaws.com/assets.sugester.pl/assets/default/avatar_thumb.png" />
                            </a>

                        </span>


                    {{/each}}                       



                    <span class="label label-info anonim" title="!! Głosy anonimowe: {{votes_count}} ">

                        <strong>+ {{votes_count}}</strong>
                        <span>anonim</span>

                    </span>                    

           

                </div> <!-- panel body -->


            </div> <!--who_voted -->


        </div> <!-- single_post -->

    </div> <!-- one_post -->


    <div id="comments" class="row">

        <div class="col-sm-10 col-sm-offset-2">


        {{{comments_box}}}

        {{{add_comment_box}}}


        </div> <!-- comments -->

    </div> <!-- col-sm-10 -->


{{/with}}

{{{posts_javascript}}}

