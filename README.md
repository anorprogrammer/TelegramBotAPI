
<!DOCTYPE html>
<html class="">
  <head>
    <meta charset="utf-8">
    <title>Telegram Bot API</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta property="description" content="The Bot API is an HTTP-based interface created for developers keen on building bots for Telegram.
To learn how to create…">
    <meta property="og:title" content="Telegram Bot API">
    <meta property="og:image" content="30f729d4f304e41659">
    <meta property="og:description" content="The Bot API is an HTTP-based interface created for developers keen on building bots for Telegram.
To learn how to create…">
    <link rel="shortcut icon" href="/favicon.ico?4" type="image/x-icon" />

    <link href="/css/bootstrap.min.css?3" rel="stylesheet">
    
    <link href="/css/telegram.css?215" rel="stylesheet" media="screen">
    <style>
    </style>
  </head>
  <body class="preload">
    <div class="dev_page_wrap">
      <div class="dev_page_head navbar navbar-static-top navbar-tg">
        <div class="navbar-inner">
          <div class="container clearfix">
            <ul class="nav navbar-nav navbar-right hidden-xs"><li class="navbar-twitter"><a href="https://twitter.com/telegram" target="_blank" data-track="Follow/Twitter" onclick="trackDlClick(this, event)"><i class="icon icon-twitter"></i><span> Twitter</span></a></li></ul>
            <ul class="nav navbar-nav">
              <li><a href="//telegram.org/">Bosh sahifa</a></li>
<li class="hidden-xs"><a href="//telegram.org/faq">FAQ</a></li>
<li class="hidden-xs"><a href="//telegram.org/apps">Ilovalar</a></li>
<li class=""><a href="/api">API</a></li>
<li class=""><a href="/mtproto">Protokol</a></li>
<li class=""><a href="/schema">Sxema</a></li>
            </ul>
          </div>
        </div>
      </div>
      <div class="container clearfix">
        <div class="dev_page">
          <div id="dev_page_content_wrap" class=" ">
  <div class="dev_page_bread_crumbs"><ul class="breadcrumb clearfix"><li><a  href="/bots" >Telegram Bots</a></li><i class="icon icon-breadcrumb-divider"></i><li><a  href="/bots/api" >Telegram Bot API</a></li></ul></div>
  <h1 id="dev_page_title">Telegram Bot API</h1>
  
  <div id="dev_page_content"><!-- scroll_nav -->

<blockquote>
<p>The Bot API is an HTTP-based interface created for developers keen on building bots for Telegram.<br>To learn how to create and set up a bot, please consult our <a href="https://core.telegram.org/bots"><strong>Introduction to Bots</strong></a> and <a href="/bots/faq"><strong>Bot FAQ</strong></a>.</p>
</blockquote>
<h3><a class="anchor" name="recent-changes" href="#recent-changes"><i class="anchor-icon"></i></a>Recent changes</h3>
<blockquote>
<p>Subscribe to <a href="https://t.me/botnews">@BotNews</a> to be the first to know about the latest updates and join the discussion in <a href="https://t.me/bottalk">@BotTalk</a></p>
</blockquote>
<h4><a class="anchor" name="january-31-2022" href="#january-31-2022"><i class="anchor-icon"></i></a>January 31, 2022</h4>
<p><strong>Bot API 5.7</strong></p>
<ul>
<li>Added support for <a href="https://telegram.org/blog/video-stickers-better-reactions">Video Stickers</a>.</li>
<li>Added the field <em>is_video</em> to the classes <a href="#sticker">Sticker</a> and <a href="#stickerset">StickerSet</a>.</li>
<li>Added the parameter <em>webm_sticker</em> to the methods <a href="#createnewstickerset">createNewStickerSet</a> and <a href="#addstickertoset">addStickerToSet</a>.</li>
</ul>
<h4><a class="anchor" name="december-30-2021" href="#december-30-2021"><i class="anchor-icon"></i></a>December 30, 2021</h4>
<p><strong>Bot API 5.6</strong></p>
<ul>
<li>Improved support for <a href="https://telegram.org/blog/protected-content-delete-by-date-and-more#protected-content-in-groups-and-channels">Protected Content</a>.</li>
<li>Added the parameter <em>protect_content</em> to the methods <a href="#sendmessage">sendMessage</a>, <a href="#sendphoto">sendPhoto</a>, <a href="#sendvideo">sendVideo</a>, <a href="#sendanimation">sendAnimation</a>, <a href="#sendaudio">sendAudio</a>, <a href="#senddocument">sendDocument</a>, <a href="#sendsticker">sendSticker</a>, <a href="#sendvideonote">sendVideoNote</a>, <a href="#sendvoice">sendVoice</a>, <a href="#sendlocation">sendLocation</a>, <a href="#sendvenue">sendVenue</a>, <a href="#sendcontact">sendContact</a>, <a href="#sendpoll">sendPoll</a>, <a href="#senddice">sendDice</a>, <a href="#sendinvoice">sendInvoice</a>, <a href="#sendgame">sendGame</a>, <a href="#sendmediagroup">sendMediaGroup</a>, <a href="#copymessage">copyMessage</a>, <a href="#forwardmessage">forwardMessage</a> to allow sending messages with protected content to any chat.</li>
<li>Added support for <a href="https://telegram.org/blog/reactions-spoilers-translations#spoilers">spoiler entities</a>, which will work in Telegram versions released after December 30, 2021. Older clients will display <em>unsupported message</em>.</li>
<li>Added new <a href="#messageentity">MessageEntity</a> type “spoiler”.</li>
<li>Added the ability to specify spoiler entities using <a href="#html-style">HTML</a> and <a href="#markdownv2-style">MarkdownV2</a> formatting options.</li>
</ul>
<h4><a class="anchor" name="december-7-2021" href="#december-7-2021"><i class="anchor-icon"></i></a>December 7, 2021</h4>
<p><strong>Bot API 5.5</strong></p>
<ul>
<li>Bots are now allowed to contact users who sent a join request to a chat where the bot is an administrator with the <em>can_invite_users</em> administrator right – even if the user never interacted with the bot before.</li>
<li>Added support for mentioning users by their ID in inline keyboards. This will only work in Telegram versions released after December 7, 2021. Older clients will display <em>unsupported message</em>.</li>
<li>Added the methods <a href="#banchatsenderchat">banChatSenderChat</a> and <a href="#unbanchatsenderchat">unbanChatSenderChat</a> for banning and unbanning channel chats in supergroups and channels.</li>
<li>Added the field <em>has_private_forwards</em> to the class <a href="#chat">Chat</a> for private chats, which can be used to check the possibility of mentioning the user by their ID.</li>
<li>Added the field <em>has_protected_content</em> to the classes <a href="#chat">Chat</a> and <a href="#message">Message</a>.</li>
<li>Added the field <em>is_automatic_forward</em> to the class <a href="#message">Message</a>.</li>
</ul>
<p><strong>Note:</strong> After this update it will become impossible to forward messages from some chats. Use the fields <em>has_protected_content</em> in the classes <a href="#message">Message</a> and <a href="#chat">Chat</a> to check this.</p>
<p><strong>Note:</strong> After this update users are able to send messages on behalf of channels they own. Bots are expected to use the field <em>sender_chat</em> in the class <a href="#message">Message</a> to correctly support such messages.</p>
<p><strong>Note:</strong> As previously announced, user identifiers can now have up to 52 significant bits and require a 64-bit integer or double-precision float type to be stored safely.</p>
<h4><a class="anchor" name="november-5-2021" href="#november-5-2021"><i class="anchor-icon"></i></a>November 5, 2021</h4>
<p><strong>Bot API 5.4</strong></p>
<ul>
<li>Added the the parameter <code>creates_join_request</code> to the methods <a href="#createchatinvitelink">createChatInviteLink</a> and <a href="#editchatinvitelink">editChatInviteLink</a> for managing chat invite links that create join requests (read more about this on our <a href="https://telegram.org/blog/shared-media-scrolling-calendar-join-requests-and-more#join-requests-for-groups-and-channels">blog</a>).</li>
<li>Added the fields <code>creates_join_request</code> and <code>pending_join_request_count</code> to the class <a href="#chatinvitelink">ChatInviteLink</a>.</li>
<li>Added the field <code>name</code> to the class <a href="#chatinvitelink">ChatInviteLink</a> and the parameters <code>name</code> to the methods <a href="#createchatinvitelink">createChatInviteLink</a> and <a href="#editchatinvitelink">editChatInviteLink</a> for managing <a href="https://telegram.org/blog/shared-media-scrolling-calendar-join-requests-and-more#unique-names-for-invite-links">invite link names</a>.</li>
<li>Added updates about new requests to join the chat, represented by the class <a href="#chatjoinrequest">ChatJoinRequest</a> and the field <em>chat_join_request</em> in the <a href="#update">Update</a> class. The bot must be an administrator in the chat with the <em>can_invite_users</em> administrator right to receive these updates.</li>
<li>Added the methods <a href="#approvechatjoinrequest">approveChatJoinRequest</a> and <a href="#declinechatjoinrequest">declineChatJoinRequest</a> for managing requests to join the chat.</li>
<li>Added support for the <em>choose_sticker</em> action in the method <a href="#sendchataction">sendChatAction</a>.</li>
</ul>
<p><strong><a href="/bots/api-changelog">See earlier changes »</a></strong></p>
<h3><a class="anchor" name="authorizing-your-bot" href="#authorizing-your-bot"><i class="anchor-icon"></i></a>Authorizing your bot</h3>
<p>Each bot is given a unique authentication token <a href="/bots#6-botfather">when it is created</a>. The token looks something like <code>123456:ABC-DEF1234ghIkl-zyx57W2v1u123ew11</code>, but we&#39;ll use simply <strong>&lt;token&gt;</strong> in this document instead. You can learn about obtaining tokens and generating new ones in <a href="https://core.telegram.org/bots#6-botfather">this document</a>.</p>
<h3><a class="anchor" name="making-requests" href="#making-requests"><i class="anchor-icon"></i></a>Making requests</h3>
<p>All queries to the Telegram Bot API must be served over HTTPS and need to be presented in this form: <code>https://api.telegram.org/bot&lt;token&gt;/METHOD_NAME</code>. Like this for example:</p>
<pre><code>https://api.telegram.org/bot123456:ABC-DEF1234ghIkl-zyx57W2v1u123ew11/getMe</code></pre>
<p>We support <strong>GET</strong> and <strong>POST</strong> HTTP methods. We support four ways of passing parameters in Bot API requests:</p>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Query_string">URL query string</a></li>
<li>application/x-www-form-urlencoded</li>
<li>application/json (except for uploading files)</li>
<li>multipart/form-data (use to upload files)</li>
</ul>
<p>The response contains a JSON object, which always has a Boolean field &#39;ok&#39; and may have an optional String field &#39;description&#39; with a human-readable description of the result. If &#39;ok&#39; equals <em>True</em>, the request was successful and the result of the query can be found in the &#39;result&#39; field. In case of an unsuccessful request, &#39;ok&#39; equals false and the error is explained in the &#39;description&#39;. An Integer &#39;error_code&#39; field is also returned, but its contents are subject to change in the future. Some errors may also have an optional field &#39;parameters&#39; of the type <a href="#responseparameters">ResponseParameters</a>, which can help to automatically handle the error.</p>
<ul>
<li>All methods in the Bot API are case-insensitive.</li>
<li>All queries must be made using UTF-8.</li>
</ul>
<h4><a class="anchor" name="making-requests-when-getting-updates" href="#making-requests-when-getting-updates"><i class="anchor-icon"></i></a>Making requests when getting updates</h4>
<p>If you&#39;re using <a href="#getting-updates"><strong>webhooks</strong></a>, you can perform a request to the Bot API while sending an answer to the webhook. Use either <em>application/json</em> or <em>application/x-www-form-urlencoded</em> or <em>multipart/form-data</em> response content type for passing parameters. Specify the method to be invoked in the <em>method</em> parameter of the request. It&#39;s not possible to know that such a request was successful or get its result.</p>
<blockquote>
<p>Please see our <a href="/bots/faq#how-can-i-make-requests-in-response-to-updates">FAQ</a> for examples.</p>
</blockquote>
<h3><a class="anchor" name="using-a-local-bot-api-server" href="#using-a-local-bot-api-server"><i class="anchor-icon"></i></a>Using a Local Bot API Server</h3>
<p>The Bot API server source code is available at <a href="https://github.com/tdlib/telegram-bot-api">telegram-bot-api</a>. You can run it locally and send the requests to your own server instead of <code>https://api.telegram.org</code>. If you switch to a local Bot API server, your bot will be able to:</p>
<ul>
<li>Download files without a size limit.</li>
<li>Upload files up to 2000 MB.</li>
<li>Upload files using their local path and <a href="https://en.wikipedia.org/wiki/File_URI_scheme">the file URI scheme</a>.</li>
<li>Use an HTTP URL for the webhook.</li>
<li>Use any local IP address for the webhook.</li>
<li>Use any port for the webhook.</li>
<li>Set <em>max_webhook_connections</em> up to 100000.</li>
<li>Receive the absolute local path as a value of the <em>file_path</em> field without the need to download the file after a <a href="#getfile">getFile</a> request.</li>
</ul>
<h4><a class="anchor" name="do-i-need-a-local-bot-api-server" href="#do-i-need-a-local-bot-api-server"><i class="anchor-icon"></i></a>Do I need a Local Bot API Server</h4>
<p>The majority of bots will be OK with the default configuration, running on our servers. But if you feel that you need one of <a href="#using-a-local-bot-api-server">these features</a>, you&#39;re welcome to switch to your own at any time.</p>
<h3><a class="anchor" name="getting-updates" href="#getting-updates"><i class="anchor-icon"></i></a>Getting updates</h3>
<p>There are two mutually exclusive ways of receiving updates for your bot — the <a href="#getupdates">getUpdates</a> method on one hand and <a href="#setwebhook">Webhooks</a> on the other. Incoming updates are stored on the server until the bot receives them either way, but they will not be kept longer than 24 hours.</p>
<p>Regardless of which option you choose, you will receive JSON-serialized <a href="#update">Update</a> objects as a result.</p>
<h4><a class="anchor" name="update" href="#update"><i class="anchor-icon"></i></a>Update</h4>
<p>This <a href="#available-types">object</a> represents an incoming update.<br>At most <strong>one</strong> of the optional parameters can be present in any given update.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>update_id</td>
<td>Integer</td>
<td>The update&#39;s unique identifier. Update identifiers start from a certain positive number and increase sequentially. This ID becomes especially handy if you&#39;re using <a href="#setwebhook">Webhooks</a>, since it allows you to ignore repeated updates or to restore the correct update sequence, should they get out of order. If there are no new updates for at least a week, then identifier of the next update will be chosen randomly instead of sequentially.</td>
</tr>
<tr>
<td>message</td>
<td><a href="#message">Message</a></td>
<td><em>Optional</em>. New incoming message of any kind — text, photo, sticker, etc.</td>
</tr>
<tr>
<td>edited_message</td>
<td><a href="#message">Message</a></td>
<td><em>Optional</em>. New version of a message that is known to the bot and was edited</td>
</tr>
<tr>
<td>channel_post</td>
<td><a href="#message">Message</a></td>
<td><em>Optional</em>. New incoming channel post of any kind — text, photo, sticker, etc.</td>
</tr>
<tr>
<td>edited_channel_post</td>
<td><a href="#message">Message</a></td>
<td><em>Optional</em>. New version of a channel post that is known to the bot and was edited</td>
</tr>
<tr>
<td>inline_query</td>
<td><a href="#inlinequery">InlineQuery</a></td>
<td><em>Optional</em>. New incoming <a href="#inline-mode">inline</a> query</td>
</tr>
<tr>
<td>chosen_inline_result</td>
<td><a href="#choseninlineresult">ChosenInlineResult</a></td>
<td><em>Optional</em>. The result of an <a href="#inline-mode">inline</a> query that was chosen by a user and sent to their chat partner. Please see our documentation on the <a href="/bots/inline#collecting-feedback">feedback collecting</a> for details on how to enable these updates for your bot.</td>
</tr>
<tr>
<td>callback_query</td>
<td><a href="#callbackquery">CallbackQuery</a></td>
<td><em>Optional</em>. New incoming callback query</td>
</tr>
<tr>
<td>shipping_query</td>
<td><a href="#shippingquery">ShippingQuery</a></td>
<td><em>Optional</em>. New incoming shipping query. Only for invoices with flexible price</td>
</tr>
<tr>
<td>pre_checkout_query</td>
<td><a href="#precheckoutquery">PreCheckoutQuery</a></td>
<td><em>Optional</em>. New incoming pre-checkout query. Contains full information about checkout</td>
</tr>
<tr>
<td>poll</td>
<td><a href="#poll">Poll</a></td>
<td><em>Optional</em>. New poll state. Bots receive only updates about stopped polls and polls, which are sent by the bot</td>
</tr>
<tr>
<td>poll_answer</td>
<td><a href="#pollanswer">PollAnswer</a></td>
<td><em>Optional</em>. A user changed their answer in a non-anonymous poll. Bots receive new votes only in polls that were sent by the bot itself.</td>
</tr>
<tr>
<td>my_chat_member</td>
<td><a href="#chatmemberupdated">ChatMemberUpdated</a></td>
<td><em>Optional</em>. The bot&#39;s chat member status was updated in a chat. For private chats, this update is received only when the bot is blocked or unblocked by the user.</td>
</tr>
<tr>
<td>chat_member</td>
<td><a href="#chatmemberupdated">ChatMemberUpdated</a></td>
<td><em>Optional</em>. A chat member&#39;s status was updated in a chat. The bot must be an administrator in the chat and must explicitly specify “chat_member” in the list of <em>allowed_updates</em> to receive these updates.</td>
</tr>
<tr>
<td>chat_join_request</td>
<td><a href="#chatjoinrequest">ChatJoinRequest</a></td>
<td><em>Optional</em>. A request to join the chat has been sent. The bot must have the <em>can_invite_users</em> administrator right in the chat to receive these updates.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="getupdates" href="#getupdates"><i class="anchor-icon"></i></a>getUpdates</h4>
<p>Use this method to receive incoming updates using long polling (<a href="https://en.wikipedia.org/wiki/Push_technology#Long_polling">wiki</a>). An Array of <a href="#update">Update</a> objects is returned.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>offset</td>
<td>Integer</td>
<td>Optional</td>
<td>Identifier of the first update to be returned. Must be greater by one than the highest among the identifiers of previously received updates. By default, updates starting with the earliest unconfirmed update are returned. An update is considered confirmed as soon as <a href="#getupdates">getUpdates</a> is called with an <em>offset</em> higher than its <em>update_id</em>. The negative offset can be specified to retrieve updates starting from <em>-offset</em> update from the end of the updates queue. All previous updates will forgotten.</td>
</tr>
<tr>
<td>limit</td>
<td>Integer</td>
<td>Optional</td>
<td>Limits the number of updates to be retrieved. Values between 1-100 are accepted. Defaults to 100.</td>
</tr>
<tr>
<td>timeout</td>
<td>Integer</td>
<td>Optional</td>
<td>Timeout in seconds for long polling. Defaults to 0, i.e. usual short polling. Should be positive, short polling should be used for testing purposes only.</td>
</tr>
<tr>
<td>allowed_updates</td>
<td>Array of String</td>
<td>Optional</td>
<td>A JSON-serialized list of the update types you want your bot to receive. For example, specify [“message”, “edited_channel_post”, “callback_query”] to only receive updates of these types. See <a href="#update">Update</a> for a complete list of available update types. Specify an empty list to receive all update types except <em>chat_member</em> (default). If not specified, the previous setting will be used.<br><br>Please note that this parameter doesn&#39;t affect updates created before the call to the getUpdates, so unwanted updates may be received for a short period of time.</td>
</tr>
</tbody>
</table>
<blockquote>
<p><strong>Notes</strong><br><strong>1.</strong> This method will not work if an outgoing webhook is set up.<br><strong>2.</strong> In order to avoid getting duplicate updates, recalculate <em>offset</em> after each server response.</p>
</blockquote>
<h4><a class="anchor" name="setwebhook" href="#setwebhook"><i class="anchor-icon"></i></a>setWebhook</h4>
<p>Use this method to specify a url and receive incoming updates via an outgoing webhook. Whenever there is an update for the bot, we will send an HTTPS POST request to the specified url, containing a JSON-serialized <a href="#update">Update</a>. In case of an unsuccessful request, we will give up after a reasonable amount of attempts. Returns <em>True</em> on success.</p>
<p>If you&#39;d like to make sure that the Webhook request comes from Telegram, we recommend using a secret path in the URL, e.g. <code>https://www.example.com/&lt;token&gt;</code>. Since nobody else knows your bot&#39;s token, you can be pretty sure it&#39;s us.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>url</td>
<td>String</td>
<td>Yes</td>
<td>HTTPS url to send updates to. Use an empty string to remove webhook integration</td>
</tr>
<tr>
<td>certificate</td>
<td><a href="#inputfile">InputFile</a></td>
<td>Optional</td>
<td>Upload your public key certificate so that the root certificate in use can be checked. See our <a href="/bots/self-signed">self-signed guide</a> for details.</td>
</tr>
<tr>
<td>ip_address</td>
<td>String</td>
<td>Optional</td>
<td>The fixed IP address which will be used to send webhook requests instead of the IP address resolved through DNS</td>
</tr>
<tr>
<td>max_connections</td>
<td>Integer</td>
<td>Optional</td>
<td>Maximum allowed number of simultaneous HTTPS connections to the webhook for update delivery, 1-100. Defaults to <em>40</em>. Use lower values to limit the load on your bot&#39;s server, and higher values to increase your bot&#39;s throughput.</td>
</tr>
<tr>
<td>allowed_updates</td>
<td>Array of String</td>
<td>Optional</td>
<td>A JSON-serialized list of the update types you want your bot to receive. For example, specify [“message”, “edited_channel_post”, “callback_query”] to only receive updates of these types. See <a href="#update">Update</a> for a complete list of available update types. Specify an empty list to receive all update types except <em>chat_member</em> (default). If not specified, the previous setting will be used.<br>Please note that this parameter doesn&#39;t affect updates created before the call to the setWebhook, so unwanted updates may be received for a short period of time.</td>
</tr>
<tr>
<td>drop_pending_updates</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em> to drop all pending updates</td>
</tr>
</tbody>
</table>
<blockquote>
<p><strong>Notes</strong><br><strong>1.</strong> You will not be able to receive updates using <a href="#getupdates">getUpdates</a> for as long as an outgoing webhook is set up.<br><strong>2.</strong> To use a self-signed certificate, you need to upload your <a href="/bots/self-signed">public key certificate</a> using <em>certificate</em> parameter. Please upload as InputFile, sending a String will not work.<br><strong>3.</strong> Ports currently supported <em>for Webhooks</em>: <strong>443, 80, 88, 8443</strong>.</p>
<p><strong>NEW!</strong> If you&#39;re having any trouble setting up webhooks, please check out this <a href="/bots/webhooks">amazing guide to Webhooks</a>.</p>
</blockquote>
<h4><a class="anchor" name="deletewebhook" href="#deletewebhook"><i class="anchor-icon"></i></a>deleteWebhook</h4>
<p>Use this method to remove webhook integration if you decide to switch back to <a href="#getupdates">getUpdates</a>. Returns <em>True</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>drop_pending_updates</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em> to drop all pending updates</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="getwebhookinfo" href="#getwebhookinfo"><i class="anchor-icon"></i></a>getWebhookInfo</h4>
<p>Use this method to get current webhook status. Requires no parameters. On success, returns a <a href="#webhookinfo">WebhookInfo</a> object. If the bot is using <a href="#getupdates">getUpdates</a>, will return an object with the <em>url</em> field empty.</p>
<h4><a class="anchor" name="webhookinfo" href="#webhookinfo"><i class="anchor-icon"></i></a>WebhookInfo</h4>
<p>Contains information about the current status of a webhook.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>url</td>
<td>String</td>
<td>Webhook URL, may be empty if webhook is not set up</td>
</tr>
<tr>
<td>has_custom_certificate</td>
<td>Boolean</td>
<td><em>True</em>, if a custom certificate was provided for webhook certificate checks</td>
</tr>
<tr>
<td>pending_update_count</td>
<td>Integer</td>
<td>Number of updates awaiting delivery</td>
</tr>
<tr>
<td>ip_address</td>
<td>String</td>
<td><em>Optional</em>. Currently used webhook IP address</td>
</tr>
<tr>
<td>last_error_date</td>
<td>Integer</td>
<td><em>Optional</em>. Unix time for the most recent error that happened when trying to deliver an update via webhook</td>
</tr>
<tr>
<td>last_error_message</td>
<td>String</td>
<td><em>Optional</em>. Error message in human-readable format for the most recent error that happened when trying to deliver an update via webhook</td>
</tr>
<tr>
<td>max_connections</td>
<td>Integer</td>
<td><em>Optional</em>. Maximum allowed number of simultaneous HTTPS connections to the webhook for update delivery</td>
</tr>
<tr>
<td>allowed_updates</td>
<td>Array of String</td>
<td><em>Optional</em>. A list of update types the bot is subscribed to. Defaults to all update types except <em>chat_member</em></td>
</tr>
</tbody>
</table>
<h3><a class="anchor" name="available-types" href="#available-types"><i class="anchor-icon"></i></a>Available types</h3>
<p>All types used in the Bot API responses are represented as JSON-objects.</p>
<p>It is safe to use 32-bit signed integers for storing all <strong>Integer</strong> fields unless otherwise noted.</p>
<blockquote>
<p><strong>Optional</strong> fields may be not returned when irrelevant.</p>
</blockquote>
<h4><a class="anchor" name="user" href="#user"><i class="anchor-icon"></i></a>User</h4>
<p>This object represents a Telegram user or bot.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>id</td>
<td>Integer</td>
<td>Unique identifier for this user or bot. This number may have more than 32 significant bits and some programming languages may have difficulty/silent defects in interpreting it. But it has at most 52 significant bits, so a 64-bit integer or double-precision float type are safe for storing this identifier.</td>
</tr>
<tr>
<td>is_bot</td>
<td>Boolean</td>
<td><em>True</em>, if this user is a bot</td>
</tr>
<tr>
<td>first_name</td>
<td>String</td>
<td>User&#39;s or bot&#39;s first name</td>
</tr>
<tr>
<td>last_name</td>
<td>String</td>
<td><em>Optional</em>. User&#39;s or bot&#39;s last name</td>
</tr>
<tr>
<td>username</td>
<td>String</td>
<td><em>Optional</em>. User&#39;s or bot&#39;s username</td>
</tr>
<tr>
<td>language_code</td>
<td>String</td>
<td><em>Optional</em>. <a href="https://en.wikipedia.org/wiki/IETF_language_tag">IETF language tag</a> of the user&#39;s language</td>
</tr>
<tr>
<td>can_join_groups</td>
<td>Boolean</td>
<td><em>Optional</em>. <em>True</em>, if the bot can be invited to groups. Returned only in <a href="#getme">getMe</a>.</td>
</tr>
<tr>
<td>can_read_all_group_messages</td>
<td>Boolean</td>
<td><em>Optional</em>. <em>True</em>, if <a href="https://core.telegram.org/bots#privacy-mode">privacy mode</a> is disabled for the bot. Returned only in <a href="#getme">getMe</a>.</td>
</tr>
<tr>
<td>supports_inline_queries</td>
<td>Boolean</td>
<td><em>Optional</em>. <em>True</em>, if the bot supports inline queries. Returned only in <a href="#getme">getMe</a>.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="chat" href="#chat"><i class="anchor-icon"></i></a>Chat</h4>
<p>This object represents a chat.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>id</td>
<td>Integer</td>
<td>Unique identifier for this chat. This number may have more than 32 significant bits and some programming languages may have difficulty/silent defects in interpreting it. But it has at most 52 significant bits, so a signed 64-bit integer or double-precision float type are safe for storing this identifier.</td>
</tr>
<tr>
<td>type</td>
<td>String</td>
<td>Type of chat, can be either “private”, “group”, “supergroup” or “channel”</td>
</tr>
<tr>
<td>title</td>
<td>String</td>
<td><em>Optional</em>. Title, for supergroups, channels and group chats</td>
</tr>
<tr>
<td>username</td>
<td>String</td>
<td><em>Optional</em>. Username, for private chats, supergroups and channels if available</td>
</tr>
<tr>
<td>first_name</td>
<td>String</td>
<td><em>Optional</em>. First name of the other party in a private chat</td>
</tr>
<tr>
<td>last_name</td>
<td>String</td>
<td><em>Optional</em>. Last name of the other party in a private chat</td>
</tr>
<tr>
<td>photo</td>
<td><a href="#chatphoto">ChatPhoto</a></td>
<td><em>Optional</em>. Chat photo. Returned only in <a href="#getchat">getChat</a>.</td>
</tr>
<tr>
<td>bio</td>
<td>String</td>
<td><em>Optional</em>. Bio of the other party in a private chat. Returned only in <a href="#getchat">getChat</a>.</td>
</tr>
<tr>
<td>has_private_forwards</td>
<td>True</td>
<td><em>Optional</em>. True, if privacy settings of the other party in the private chat allows to use <code>tg://user?id=&lt;user_id&gt;</code> links only in chats with the user. Returned only in <a href="#getchat">getChat</a>.</td>
</tr>
<tr>
<td>description</td>
<td>String</td>
<td><em>Optional</em>. Description, for groups, supergroups and channel chats. Returned only in <a href="#getchat">getChat</a>.</td>
</tr>
<tr>
<td>invite_link</td>
<td>String</td>
<td><em>Optional</em>. Primary invite link, for groups, supergroups and channel chats. Returned only in <a href="#getchat">getChat</a>.</td>
</tr>
<tr>
<td>pinned_message</td>
<td><a href="#message">Message</a></td>
<td><em>Optional</em>. The most recent pinned message (by sending date). Returned only in <a href="#getchat">getChat</a>.</td>
</tr>
<tr>
<td>permissions</td>
<td><a href="#chatpermissions">ChatPermissions</a></td>
<td><em>Optional</em>. Default chat member permissions, for groups and supergroups. Returned only in <a href="#getchat">getChat</a>.</td>
</tr>
<tr>
<td>slow_mode_delay</td>
<td>Integer</td>
<td><em>Optional</em>. For supergroups, the minimum allowed delay between consecutive messages sent by each unpriviledged user; in seconds. Returned only in <a href="#getchat">getChat</a>.</td>
</tr>
<tr>
<td>message_auto_delete_time</td>
<td>Integer</td>
<td><em>Optional</em>. The time after which all messages sent to the chat will be automatically deleted; in seconds. Returned only in <a href="#getchat">getChat</a>.</td>
</tr>
<tr>
<td>has_protected_content</td>
<td>True</td>
<td><em>Optional</em>. True, if messages from the chat can&#39;t be forwarded to other chats. Returned only in <a href="#getchat">getChat</a>.</td>
</tr>
<tr>
<td>sticker_set_name</td>
<td>String</td>
<td><em>Optional</em>. For supergroups, name of group sticker set. Returned only in <a href="#getchat">getChat</a>.</td>
</tr>
<tr>
<td>can_set_sticker_set</td>
<td>True</td>
<td><em>Optional</em>. <em>True</em>, if the bot can change the group sticker set. Returned only in <a href="#getchat">getChat</a>.</td>
</tr>
<tr>
<td>linked_chat_id</td>
<td>Integer</td>
<td><em>Optional</em>. Unique identifier for the linked chat, i.e. the discussion group identifier for a channel and vice versa; for supergroups and channel chats. This identifier may be greater than 32 bits and some programming languages may have difficulty/silent defects in interpreting it. But it is smaller than 52 bits, so a signed 64 bit integer or double-precision float type are safe for storing this identifier. Returned only in <a href="#getchat">getChat</a>.</td>
</tr>
<tr>
<td>location</td>
<td><a href="#chatlocation">ChatLocation</a></td>
<td><em>Optional</em>. For supergroups, the location to which the supergroup is connected. Returned only in <a href="#getchat">getChat</a>.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="message" href="#message"><i class="anchor-icon"></i></a>Message</h4>
<p>This object represents a message.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>message_id</td>
<td>Integer</td>
<td>Unique message identifier inside this chat</td>
</tr>
<tr>
<td>from</td>
<td><a href="#user">User</a></td>
<td><em>Optional</em>. Sender of the message; empty for messages sent to channels. For backward compatibility, the field contains a fake sender user in non-channel chats, if the message was sent on behalf of a chat.</td>
</tr>
<tr>
<td>sender_chat</td>
<td><a href="#chat">Chat</a></td>
<td><em>Optional</em>. Sender of the message, sent on behalf of a chat. For example, the channel itself for channel posts, the supergroup itself for messages from anonymous group administrators, the linked channel for messages automatically forwarded to the discussion group.  For backward compatibility, the field <em>from</em> contains a fake sender user in non-channel chats, if the message was sent on behalf of a chat.</td>
</tr>
<tr>
<td>date</td>
<td>Integer</td>
<td>Date the message was sent in Unix time</td>
</tr>
<tr>
<td>chat</td>
<td><a href="#chat">Chat</a></td>
<td>Conversation the message belongs to</td>
</tr>
<tr>
<td>forward_from</td>
<td><a href="#user">User</a></td>
<td><em>Optional</em>. For forwarded messages, sender of the original message</td>
</tr>
<tr>
<td>forward_from_chat</td>
<td><a href="#chat">Chat</a></td>
<td><em>Optional</em>. For messages forwarded from channels or from anonymous administrators, information about the original sender chat</td>
</tr>
<tr>
<td>forward_from_message_id</td>
<td>Integer</td>
<td><em>Optional</em>. For messages forwarded from channels, identifier of the original message in the channel</td>
</tr>
<tr>
<td>forward_signature</td>
<td>String</td>
<td><em>Optional</em>. For forwarded messages that were originally sent in channels or by an anonymous chat administrator, signature of the message sender if present</td>
</tr>
<tr>
<td>forward_sender_name</td>
<td>String</td>
<td><em>Optional</em>. Sender&#39;s name for messages forwarded from users who disallow adding a link to their account in forwarded messages</td>
</tr>
<tr>
<td>forward_date</td>
<td>Integer</td>
<td><em>Optional</em>. For forwarded messages, date the original message was sent in Unix time</td>
</tr>
<tr>
<td>is_automatic_forward</td>
<td>True</td>
<td><em>Optional</em>. True, if the message is a channel post that was automatically forwarded to the connected discussion group</td>
</tr>
<tr>
<td>reply_to_message</td>
<td><a href="#message">Message</a></td>
<td><em>Optional</em>. For replies, the original message. Note that the Message object in this field will not contain further <em>reply_to_message</em> fields even if it itself is a reply.</td>
</tr>
<tr>
<td>via_bot</td>
<td><a href="#user">User</a></td>
<td><em>Optional</em>. Bot through which the message was sent</td>
</tr>
<tr>
<td>edit_date</td>
<td>Integer</td>
<td><em>Optional</em>. Date the message was last edited in Unix time</td>
</tr>
<tr>
<td>has_protected_content</td>
<td>True</td>
<td><em>Optional</em>. True, if the message can&#39;t be forwarded</td>
</tr>
<tr>
<td>media_group_id</td>
<td>String</td>
<td><em>Optional</em>. The unique identifier of a media message group this message belongs to</td>
</tr>
<tr>
<td>author_signature</td>
<td>String</td>
<td><em>Optional</em>. Signature of the post author for messages in channels, or the custom title of an anonymous group administrator</td>
</tr>
<tr>
<td>text</td>
<td>String</td>
<td><em>Optional</em>. For text messages, the actual UTF-8 text of the message, 0-4096 characters</td>
</tr>
<tr>
<td>entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td><em>Optional</em>. For text messages, special entities like usernames, URLs, bot commands, etc. that appear in the text</td>
</tr>
<tr>
<td>animation</td>
<td><a href="#animation">Animation</a></td>
<td><em>Optional</em>. Message is an animation, information about the animation. For backward compatibility, when this field is set, the <em>document</em> field will also be set</td>
</tr>
<tr>
<td>audio</td>
<td><a href="#audio">Audio</a></td>
<td><em>Optional</em>. Message is an audio file, information about the file</td>
</tr>
<tr>
<td>document</td>
<td><a href="#document">Document</a></td>
<td><em>Optional</em>. Message is a general file, information about the file</td>
</tr>
<tr>
<td>photo</td>
<td>Array of <a href="#photosize">PhotoSize</a></td>
<td><em>Optional</em>. Message is a photo, available sizes of the photo</td>
</tr>
<tr>
<td>sticker</td>
<td><a href="#sticker">Sticker</a></td>
<td><em>Optional</em>. Message is a sticker, information about the sticker</td>
</tr>
<tr>
<td>video</td>
<td><a href="#video">Video</a></td>
<td><em>Optional</em>. Message is a video, information about the video</td>
</tr>
<tr>
<td>video_note</td>
<td><a href="#videonote">VideoNote</a></td>
<td><em>Optional</em>. Message is a <a href="https://telegram.org/blog/video-messages-and-telescope">video note</a>, information about the video message</td>
</tr>
<tr>
<td>voice</td>
<td><a href="#voice">Voice</a></td>
<td><em>Optional</em>. Message is a voice message, information about the file</td>
</tr>
<tr>
<td>caption</td>
<td>String</td>
<td><em>Optional</em>. Caption for the animation, audio, document, photo, video or voice, 0-1024 characters</td>
</tr>
<tr>
<td>caption_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td><em>Optional</em>. For messages with a caption, special entities like usernames, URLs, bot commands, etc. that appear in the caption</td>
</tr>
<tr>
<td>contact</td>
<td><a href="#contact">Contact</a></td>
<td><em>Optional</em>. Message is a shared contact, information about the contact</td>
</tr>
<tr>
<td>dice</td>
<td><a href="#dice">Dice</a></td>
<td><em>Optional</em>. Message is a dice with random value</td>
</tr>
<tr>
<td>game</td>
<td><a href="#game">Game</a></td>
<td><em>Optional</em>. Message is a game, information about the game. <a href="#games">More about games »</a></td>
</tr>
<tr>
<td>poll</td>
<td><a href="#poll">Poll</a></td>
<td><em>Optional</em>. Message is a native poll, information about the poll</td>
</tr>
<tr>
<td>venue</td>
<td><a href="#venue">Venue</a></td>
<td><em>Optional</em>. Message is a venue, information about the venue. For backward compatibility, when this field is set, the <em>location</em> field will also be set</td>
</tr>
<tr>
<td>location</td>
<td><a href="#location">Location</a></td>
<td><em>Optional</em>. Message is a shared location, information about the location</td>
</tr>
<tr>
<td>new_chat_members</td>
<td>Array of <a href="#user">User</a></td>
<td><em>Optional</em>. New members that were added to the group or supergroup and information about them (the bot itself may be one of these members)</td>
</tr>
<tr>
<td>left_chat_member</td>
<td><a href="#user">User</a></td>
<td><em>Optional</em>. A member was removed from the group, information about them (this member may be the bot itself)</td>
</tr>
<tr>
<td>new_chat_title</td>
<td>String</td>
<td><em>Optional</em>. A chat title was changed to this value</td>
</tr>
<tr>
<td>new_chat_photo</td>
<td>Array of <a href="#photosize">PhotoSize</a></td>
<td><em>Optional</em>. A chat photo was change to this value</td>
</tr>
<tr>
<td>delete_chat_photo</td>
<td>True</td>
<td><em>Optional</em>. Service message: the chat photo was deleted</td>
</tr>
<tr>
<td>group_chat_created</td>
<td>True</td>
<td><em>Optional</em>. Service message: the group has been created</td>
</tr>
<tr>
<td>supergroup_chat_created</td>
<td>True</td>
<td><em>Optional</em>. Service message: the supergroup has been created. This field can&#39;t be received in a message coming through updates, because bot can&#39;t be a member of a supergroup when it is created. It can only be found in reply_to_message if someone replies to a very first message in a directly created supergroup.</td>
</tr>
<tr>
<td>channel_chat_created</td>
<td>True</td>
<td><em>Optional</em>. Service message: the channel has been created. This field can&#39;t be received in a message coming through updates, because bot can&#39;t be a member of a channel when it is created. It can only be found in reply_to_message if someone replies to a very first message in a channel.</td>
</tr>
<tr>
<td>message_auto_delete_timer_changed</td>
<td><a href="#messageautodeletetimerchanged">MessageAutoDeleteTimerChanged</a></td>
<td><em>Optional</em>. Service message: auto-delete timer settings changed in the chat</td>
</tr>
<tr>
<td>migrate_to_chat_id</td>
<td>Integer</td>
<td><em>Optional</em>. The group has been migrated to a supergroup with the specified identifier. This number may have more than 32 significant bits and some programming languages may have difficulty/silent defects in interpreting it. But it has at most 52 significant bits, so a signed 64-bit integer or double-precision float type are safe for storing this identifier.</td>
</tr>
<tr>
<td>migrate_from_chat_id</td>
<td>Integer</td>
<td><em>Optional</em>. The supergroup has been migrated from a group with the specified identifier. This number may have more than 32 significant bits and some programming languages may have difficulty/silent defects in interpreting it. But it has at most 52 significant bits, so a signed 64-bit integer or double-precision float type are safe for storing this identifier.</td>
</tr>
<tr>
<td>pinned_message</td>
<td><a href="#message">Message</a></td>
<td><em>Optional</em>. Specified message was pinned. Note that the Message object in this field will not contain further <em>reply_to_message</em> fields even if it is itself a reply.</td>
</tr>
<tr>
<td>invoice</td>
<td><a href="#invoice">Invoice</a></td>
<td><em>Optional</em>. Message is an invoice for a <a href="#payments">payment</a>, information about the invoice. <a href="#payments">More about payments »</a></td>
</tr>
<tr>
<td>successful_payment</td>
<td><a href="#successfulpayment">SuccessfulPayment</a></td>
<td><em>Optional</em>. Message is a service message about a successful payment, information about the payment. <a href="#payments">More about payments »</a></td>
</tr>
<tr>
<td>connected_website</td>
<td>String</td>
<td><em>Optional</em>. The domain name of the website on which the user has logged in. <a href="/widgets/login">More about Telegram Login »</a></td>
</tr>
<tr>
<td>passport_data</td>
<td><a href="#passportdata">PassportData</a></td>
<td><em>Optional</em>. Telegram Passport data</td>
</tr>
<tr>
<td>proximity_alert_triggered</td>
<td><a href="#proximityalerttriggered">ProximityAlertTriggered</a></td>
<td><em>Optional</em>. Service message. A user in the chat triggered another user&#39;s proximity alert while sharing Live Location.</td>
</tr>
<tr>
<td>voice_chat_scheduled</td>
<td><a href="#voicechatscheduled">VoiceChatScheduled</a></td>
<td><em>Optional</em>. Service message: voice chat scheduled</td>
</tr>
<tr>
<td>voice_chat_started</td>
<td><a href="#voicechatstarted">VoiceChatStarted</a></td>
<td><em>Optional</em>. Service message: voice chat started</td>
</tr>
<tr>
<td>voice_chat_ended</td>
<td><a href="#voicechatended">VoiceChatEnded</a></td>
<td><em>Optional</em>. Service message: voice chat ended</td>
</tr>
<tr>
<td>voice_chat_participants_invited</td>
<td><a href="#voicechatparticipantsinvited">VoiceChatParticipantsInvited</a></td>
<td><em>Optional</em>. Service message: new participants invited to a voice chat</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a></td>
<td><em>Optional</em>. Inline keyboard attached to the message. <code>login_url</code> buttons are represented as ordinary <code>url</code> buttons.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="messageid" href="#messageid"><i class="anchor-icon"></i></a>MessageId</h4>
<p>This object represents a unique message identifier.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>message_id</td>
<td>Integer</td>
<td>Unique message identifier</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="messageentity" href="#messageentity"><i class="anchor-icon"></i></a>MessageEntity</h4>
<p>This object represents one special entity in a text message. For example, hashtags, usernames, URLs, etc.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Type of the entity. Currently, can be “mention” (<code>@username</code>), “hashtag” (<code>#hashtag</code>), “cashtag” (<code>$USD</code>), “bot_command” (<code>/start@jobs_bot</code>), “url” (<code>https://telegram.org</code>), “email” (<code>do-not-reply@telegram.org</code>), “phone_number” (<code>+1-212-555-0123</code>), “bold” (<strong>bold text</strong>), “italic” (<em>italic text</em>), “underline” (underlined text), “strikethrough” (strikethrough text), “spoiler” (spoiler message), “code” (monowidth string), “pre” (monowidth block), “text_link” (for clickable text URLs), “text_mention” (for users <a href="https://telegram.org/blog/edit#new-mentions">without usernames</a>)</td>
</tr>
<tr>
<td>offset</td>
<td>Integer</td>
<td>Offset in UTF-16 code units to the start of the entity</td>
</tr>
<tr>
<td>length</td>
<td>Integer</td>
<td>Length of the entity in UTF-16 code units</td>
</tr>
<tr>
<td>url</td>
<td>String</td>
<td><em>Optional</em>. For “text_link” only, url that will be opened after user taps on the text</td>
</tr>
<tr>
<td>user</td>
<td><a href="#user">User</a></td>
<td><em>Optional</em>. For “text_mention” only, the mentioned user</td>
</tr>
<tr>
<td>language</td>
<td>String</td>
<td><em>Optional</em>. For “pre” only, the programming language of the entity text</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="photosize" href="#photosize"><i class="anchor-icon"></i></a>PhotoSize</h4>
<p>This object represents one size of a photo or a <a href="#document">file</a> / <a href="#sticker">sticker</a> thumbnail.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>file_id</td>
<td>String</td>
<td>Identifier for this file, which can be used to download or reuse the file</td>
</tr>
<tr>
<td>file_unique_id</td>
<td>String</td>
<td>Unique identifier for this file, which is supposed to be the same over time and for different bots. Can&#39;t be used to download or reuse the file.</td>
</tr>
<tr>
<td>width</td>
<td>Integer</td>
<td>Photo width</td>
</tr>
<tr>
<td>height</td>
<td>Integer</td>
<td>Photo height</td>
</tr>
<tr>
<td>file_size</td>
<td>Integer</td>
<td><em>Optional</em>. File size in bytes</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="animation" href="#animation"><i class="anchor-icon"></i></a>Animation</h4>
<p>This object represents an animation file (GIF or H.264/MPEG-4 AVC video without sound).</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>file_id</td>
<td>String</td>
<td>Identifier for this file, which can be used to download or reuse the file</td>
</tr>
<tr>
<td>file_unique_id</td>
<td>String</td>
<td>Unique identifier for this file, which is supposed to be the same over time and for different bots. Can&#39;t be used to download or reuse the file.</td>
</tr>
<tr>
<td>width</td>
<td>Integer</td>
<td>Video width as defined by sender</td>
</tr>
<tr>
<td>height</td>
<td>Integer</td>
<td>Video height as defined by sender</td>
</tr>
<tr>
<td>duration</td>
<td>Integer</td>
<td>Duration of the video in seconds as defined by sender</td>
</tr>
<tr>
<td>thumb</td>
<td><a href="#photosize">PhotoSize</a></td>
<td><em>Optional</em>. Animation thumbnail as defined by sender</td>
</tr>
<tr>
<td>file_name</td>
<td>String</td>
<td><em>Optional</em>. Original animation filename as defined by sender</td>
</tr>
<tr>
<td>mime_type</td>
<td>String</td>
<td><em>Optional</em>. MIME type of the file as defined by sender</td>
</tr>
<tr>
<td>file_size</td>
<td>Integer</td>
<td><em>Optional</em>. File size in bytes</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="audio" href="#audio"><i class="anchor-icon"></i></a>Audio</h4>
<p>This object represents an audio file to be treated as music by the Telegram clients.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>file_id</td>
<td>String</td>
<td>Identifier for this file, which can be used to download or reuse the file</td>
</tr>
<tr>
<td>file_unique_id</td>
<td>String</td>
<td>Unique identifier for this file, which is supposed to be the same over time and for different bots. Can&#39;t be used to download or reuse the file.</td>
</tr>
<tr>
<td>duration</td>
<td>Integer</td>
<td>Duration of the audio in seconds as defined by sender</td>
</tr>
<tr>
<td>performer</td>
<td>String</td>
<td><em>Optional</em>. Performer of the audio as defined by sender or by audio tags</td>
</tr>
<tr>
<td>title</td>
<td>String</td>
<td><em>Optional</em>. Title of the audio as defined by sender or by audio tags</td>
</tr>
<tr>
<td>file_name</td>
<td>String</td>
<td><em>Optional</em>. Original filename as defined by sender</td>
</tr>
<tr>
<td>mime_type</td>
<td>String</td>
<td><em>Optional</em>. MIME type of the file as defined by sender</td>
</tr>
<tr>
<td>file_size</td>
<td>Integer</td>
<td><em>Optional</em>. File size in bytes</td>
</tr>
<tr>
<td>thumb</td>
<td><a href="#photosize">PhotoSize</a></td>
<td><em>Optional</em>. Thumbnail of the album cover to which the music file belongs</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="document" href="#document"><i class="anchor-icon"></i></a>Document</h4>
<p>This object represents a general file (as opposed to <a href="#photosize">photos</a>, <a href="#voice">voice messages</a> and <a href="#audio">audio files</a>).</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>file_id</td>
<td>String</td>
<td>Identifier for this file, which can be used to download or reuse the file</td>
</tr>
<tr>
<td>file_unique_id</td>
<td>String</td>
<td>Unique identifier for this file, which is supposed to be the same over time and for different bots. Can&#39;t be used to download or reuse the file.</td>
</tr>
<tr>
<td>thumb</td>
<td><a href="#photosize">PhotoSize</a></td>
<td><em>Optional</em>. Document thumbnail as defined by sender</td>
</tr>
<tr>
<td>file_name</td>
<td>String</td>
<td><em>Optional</em>. Original filename as defined by sender</td>
</tr>
<tr>
<td>mime_type</td>
<td>String</td>
<td><em>Optional</em>. MIME type of the file as defined by sender</td>
</tr>
<tr>
<td>file_size</td>
<td>Integer</td>
<td><em>Optional</em>. File size in bytes</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="video" href="#video"><i class="anchor-icon"></i></a>Video</h4>
<p>This object represents a video file.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>file_id</td>
<td>String</td>
<td>Identifier for this file, which can be used to download or reuse the file</td>
</tr>
<tr>
<td>file_unique_id</td>
<td>String</td>
<td>Unique identifier for this file, which is supposed to be the same over time and for different bots. Can&#39;t be used to download or reuse the file.</td>
</tr>
<tr>
<td>width</td>
<td>Integer</td>
<td>Video width as defined by sender</td>
</tr>
<tr>
<td>height</td>
<td>Integer</td>
<td>Video height as defined by sender</td>
</tr>
<tr>
<td>duration</td>
<td>Integer</td>
<td>Duration of the video in seconds as defined by sender</td>
</tr>
<tr>
<td>thumb</td>
<td><a href="#photosize">PhotoSize</a></td>
<td><em>Optional</em>. Video thumbnail</td>
</tr>
<tr>
<td>file_name</td>
<td>String</td>
<td><em>Optional</em>. Original filename as defined by sender</td>
</tr>
<tr>
<td>mime_type</td>
<td>String</td>
<td><em>Optional</em>. Mime type of a file as defined by sender</td>
</tr>
<tr>
<td>file_size</td>
<td>Integer</td>
<td><em>Optional</em>. File size in bytes</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="videonote" href="#videonote"><i class="anchor-icon"></i></a>VideoNote</h4>
<p>This object represents a <a href="https://telegram.org/blog/video-messages-and-telescope">video message</a> (available in Telegram apps as of <a href="https://telegram.org/blog/video-messages-and-telescope">v.4.0</a>).</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>file_id</td>
<td>String</td>
<td>Identifier for this file, which can be used to download or reuse the file</td>
</tr>
<tr>
<td>file_unique_id</td>
<td>String</td>
<td>Unique identifier for this file, which is supposed to be the same over time and for different bots. Can&#39;t be used to download or reuse the file.</td>
</tr>
<tr>
<td>length</td>
<td>Integer</td>
<td>Video width and height (diameter of the video message) as defined by sender</td>
</tr>
<tr>
<td>duration</td>
<td>Integer</td>
<td>Duration of the video in seconds as defined by sender</td>
</tr>
<tr>
<td>thumb</td>
<td><a href="#photosize">PhotoSize</a></td>
<td><em>Optional</em>. Video thumbnail</td>
</tr>
<tr>
<td>file_size</td>
<td>Integer</td>
<td><em>Optional</em>. File size in bytes</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="voice" href="#voice"><i class="anchor-icon"></i></a>Voice</h4>
<p>This object represents a voice note.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>file_id</td>
<td>String</td>
<td>Identifier for this file, which can be used to download or reuse the file</td>
</tr>
<tr>
<td>file_unique_id</td>
<td>String</td>
<td>Unique identifier for this file, which is supposed to be the same over time and for different bots. Can&#39;t be used to download or reuse the file.</td>
</tr>
<tr>
<td>duration</td>
<td>Integer</td>
<td>Duration of the audio in seconds as defined by sender</td>
</tr>
<tr>
<td>mime_type</td>
<td>String</td>
<td><em>Optional</em>. MIME type of the file as defined by sender</td>
</tr>
<tr>
<td>file_size</td>
<td>Integer</td>
<td><em>Optional</em>. File size in bytes</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="contact" href="#contact"><i class="anchor-icon"></i></a>Contact</h4>
<p>This object represents a phone contact.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>phone_number</td>
<td>String</td>
<td>Contact&#39;s phone number</td>
</tr>
<tr>
<td>first_name</td>
<td>String</td>
<td>Contact&#39;s first name</td>
</tr>
<tr>
<td>last_name</td>
<td>String</td>
<td><em>Optional</em>. Contact&#39;s last name</td>
</tr>
<tr>
<td>user_id</td>
<td>Integer</td>
<td><em>Optional</em>. Contact&#39;s user identifier in Telegram. This number may have more than 32 significant bits and some programming languages may have difficulty/silent defects in interpreting it. But it has at most 52 significant bits, so a 64-bit integer or double-precision float type are safe for storing this identifier.</td>
</tr>
<tr>
<td>vcard</td>
<td>String</td>
<td><em>Optional</em>. Additional data about the contact in the form of a <a href="https://en.wikipedia.org/wiki/VCard">vCard</a></td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="dice" href="#dice"><i class="anchor-icon"></i></a>Dice</h4>
<p>This object represents an animated emoji that displays a random value.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>emoji</td>
<td>String</td>
<td>Emoji on which the dice throw animation is based</td>
</tr>
<tr>
<td>value</td>
<td>Integer</td>
<td>Value of the dice, 1-6 for “<img class="emoji" src="//telegram.org/img/emoji/40/F09F8EB2.png" width="20" height="20" alt="🎲" />”, “<img class="emoji" src="//telegram.org/img/emoji/40/F09F8EAF.png" width="20" height="20" alt="🎯" />” and “<img class="emoji" src="//telegram.org/img/emoji/40/F09F8EB3.png" width="20" height="20" alt="🎳" />” base emoji, 1-5 for “<img class="emoji" src="//telegram.org/img/emoji/40/F09F8F80.png" width="20" height="20" alt="🏀" />” and “<img class="emoji" src="//telegram.org/img/emoji/40/E29ABD.png" width="20" height="20" alt="⚽" />” base emoji, 1-64 for “<img class="emoji" src="//telegram.org/img/emoji/40/F09F8EB0.png" width="20" height="20" alt="🎰" />” base emoji</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="polloption" href="#polloption"><i class="anchor-icon"></i></a>PollOption</h4>
<p>This object contains information about one answer option in a poll.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>text</td>
<td>String</td>
<td>Option text, 1-100 characters</td>
</tr>
<tr>
<td>voter_count</td>
<td>Integer</td>
<td>Number of users that voted for this option</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="pollanswer" href="#pollanswer"><i class="anchor-icon"></i></a>PollAnswer</h4>
<p>This object represents an answer of a user in a non-anonymous poll.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>poll_id</td>
<td>String</td>
<td>Unique poll identifier</td>
</tr>
<tr>
<td>user</td>
<td><a href="#user">User</a></td>
<td>The user, who changed the answer to the poll</td>
</tr>
<tr>
<td>option_ids</td>
<td>Array of Integer</td>
<td>0-based identifiers of answer options, chosen by the user. May be empty if the user retracted their vote.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="poll" href="#poll"><i class="anchor-icon"></i></a>Poll</h4>
<p>This object contains information about a poll.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>id</td>
<td>String</td>
<td>Unique poll identifier</td>
</tr>
<tr>
<td>question</td>
<td>String</td>
<td>Poll question, 1-300 characters</td>
</tr>
<tr>
<td>options</td>
<td>Array of <a href="#polloption">PollOption</a></td>
<td>List of poll options</td>
</tr>
<tr>
<td>total_voter_count</td>
<td>Integer</td>
<td>Total number of users that voted in the poll</td>
</tr>
<tr>
<td>is_closed</td>
<td>Boolean</td>
<td><em>True</em>, if the poll is closed</td>
</tr>
<tr>
<td>is_anonymous</td>
<td>Boolean</td>
<td><em>True</em>, if the poll is anonymous</td>
</tr>
<tr>
<td>type</td>
<td>String</td>
<td>Poll type, currently can be “regular” or “quiz”</td>
</tr>
<tr>
<td>allows_multiple_answers</td>
<td>Boolean</td>
<td><em>True</em>, if the poll allows multiple answers</td>
</tr>
<tr>
<td>correct_option_id</td>
<td>Integer</td>
<td><em>Optional</em>. 0-based identifier of the correct answer option. Available only for polls in the quiz mode, which are closed, or was sent (not forwarded) by the bot or to the private chat with the bot.</td>
</tr>
<tr>
<td>explanation</td>
<td>String</td>
<td><em>Optional</em>. Text that is shown when a user chooses an incorrect answer or taps on the lamp icon in a quiz-style poll, 0-200 characters</td>
</tr>
<tr>
<td>explanation_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td><em>Optional</em>. Special entities like usernames, URLs, bot commands, etc. that appear in the <em>explanation</em></td>
</tr>
<tr>
<td>open_period</td>
<td>Integer</td>
<td><em>Optional</em>. Amount of time in seconds the poll will be active after creation</td>
</tr>
<tr>
<td>close_date</td>
<td>Integer</td>
<td><em>Optional</em>. Point in time (Unix timestamp) when the poll will be automatically closed</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="location" href="#location"><i class="anchor-icon"></i></a>Location</h4>
<p>This object represents a point on the map.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>longitude</td>
<td>Float</td>
<td>Longitude as defined by sender</td>
</tr>
<tr>
<td>latitude</td>
<td>Float</td>
<td>Latitude as defined by sender</td>
</tr>
<tr>
<td>horizontal_accuracy</td>
<td>Float number</td>
<td><em>Optional</em>. The radius of uncertainty for the location, measured in meters; 0-1500</td>
</tr>
<tr>
<td>live_period</td>
<td>Integer</td>
<td><em>Optional</em>. Time relative to the message sending date, during which the location can be updated; in seconds. For active live locations only.</td>
</tr>
<tr>
<td>heading</td>
<td>Integer</td>
<td><em>Optional</em>. The direction in which user is moving, in degrees; 1-360. For active live locations only.</td>
</tr>
<tr>
<td>proximity_alert_radius</td>
<td>Integer</td>
<td><em>Optional</em>. Maximum distance for proximity alerts about approaching another chat member, in meters. For sent live locations only.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="venue" href="#venue"><i class="anchor-icon"></i></a>Venue</h4>
<p>This object represents a venue.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>location</td>
<td><a href="#location">Location</a></td>
<td>Venue location. Can&#39;t be a live location</td>
</tr>
<tr>
<td>title</td>
<td>String</td>
<td>Name of the venue</td>
</tr>
<tr>
<td>address</td>
<td>String</td>
<td>Address of the venue</td>
</tr>
<tr>
<td>foursquare_id</td>
<td>String</td>
<td><em>Optional</em>. Foursquare identifier of the venue</td>
</tr>
<tr>
<td>foursquare_type</td>
<td>String</td>
<td><em>Optional</em>. Foursquare type of the venue. (For example, “arts_entertainment/default”, “arts_entertainment/aquarium” or “food/icecream”.)</td>
</tr>
<tr>
<td>google_place_id</td>
<td>String</td>
<td><em>Optional</em>. Google Places identifier of the venue</td>
</tr>
<tr>
<td>google_place_type</td>
<td>String</td>
<td><em>Optional</em>. Google Places type of the venue. (See <a href="https://developers.google.com/places/web-service/supported_types">supported types</a>.)</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="proximityalerttriggered" href="#proximityalerttriggered"><i class="anchor-icon"></i></a>ProximityAlertTriggered</h4>
<p>This object represents the content of a service message, sent whenever a user in the chat triggers a proximity alert set by another user.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>traveler</td>
<td><a href="#user">User</a></td>
<td>User that triggered the alert</td>
</tr>
<tr>
<td>watcher</td>
<td><a href="#user">User</a></td>
<td>User that set the alert</td>
</tr>
<tr>
<td>distance</td>
<td>Integer</td>
<td>The distance between the users</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="messageautodeletetimerchanged" href="#messageautodeletetimerchanged"><i class="anchor-icon"></i></a>MessageAutoDeleteTimerChanged</h4>
<p>This object represents a service message about a change in auto-delete timer settings.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>message_auto_delete_time</td>
<td>Integer</td>
<td>New auto-delete time for messages in the chat; in seconds</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="voicechatscheduled" href="#voicechatscheduled"><i class="anchor-icon"></i></a>VoiceChatScheduled</h4>
<p>This object represents a service message about a voice chat scheduled in the chat.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>start_date</td>
<td>Integer</td>
<td>Point in time (Unix timestamp) when the voice chat is supposed to be started by a chat administrator</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="voicechatstarted" href="#voicechatstarted"><i class="anchor-icon"></i></a>VoiceChatStarted</h4>
<p>This object represents a service message about a voice chat started in the chat. Currently holds no information.</p>
<h4><a class="anchor" name="voicechatended" href="#voicechatended"><i class="anchor-icon"></i></a>VoiceChatEnded</h4>
<p>This object represents a service message about a voice chat ended in the chat.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>duration</td>
<td>Integer</td>
<td>Voice chat duration in seconds</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="voicechatparticipantsinvited" href="#voicechatparticipantsinvited"><i class="anchor-icon"></i></a>VoiceChatParticipantsInvited</h4>
<p>This object represents a service message about new members invited to a voice chat.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>users</td>
<td>Array of <a href="#user">User</a></td>
<td><em>Optional</em>. New members that were invited to the voice chat</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="userprofilephotos" href="#userprofilephotos"><i class="anchor-icon"></i></a>UserProfilePhotos</h4>
<p>This object represent a user&#39;s profile pictures.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>total_count</td>
<td>Integer</td>
<td>Total number of profile pictures the target user has</td>
</tr>
<tr>
<td>photos</td>
<td>Array of Array of <a href="#photosize">PhotoSize</a></td>
<td>Requested profile pictures (in up to 4 sizes each)</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="file" href="#file"><i class="anchor-icon"></i></a>File</h4>
<p>This object represents a file ready to be downloaded. The file can be downloaded via the link <code>https://api.telegram.org/file/bot&lt;token&gt;/&lt;file_path&gt;</code>. It is guaranteed that the link will be valid for at least 1 hour. When the link expires, a new one can be requested by calling <a href="#getfile">getFile</a>.</p>
<blockquote>
<p>Maximum file size to download is 20 MB</p>
</blockquote>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>file_id</td>
<td>String</td>
<td>Identifier for this file, which can be used to download or reuse the file</td>
</tr>
<tr>
<td>file_unique_id</td>
<td>String</td>
<td>Unique identifier for this file, which is supposed to be the same over time and for different bots. Can&#39;t be used to download or reuse the file.</td>
</tr>
<tr>
<td>file_size</td>
<td>Integer</td>
<td><em>Optional</em>. File size in bytes, if known</td>
</tr>
<tr>
<td>file_path</td>
<td>String</td>
<td><em>Optional</em>. File path. Use <code>https://api.telegram.org/file/bot&lt;token&gt;/&lt;file_path&gt;</code> to get the file.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="replykeyboardmarkup" href="#replykeyboardmarkup"><i class="anchor-icon"></i></a>ReplyKeyboardMarkup</h4>
<p>This object represents a <a href="https://core.telegram.org/bots#keyboards">custom keyboard</a> with reply options (see <a href="https://core.telegram.org/bots#keyboards">Introduction to bots</a> for details and examples).</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>keyboard</td>
<td>Array of Array of <a href="#keyboardbutton">KeyboardButton</a></td>
<td>Array of button rows, each represented by an Array of <a href="#keyboardbutton">KeyboardButton</a> objects</td>
</tr>
<tr>
<td>resize_keyboard</td>
<td>Boolean</td>
<td><em>Optional</em>. Requests clients to resize the keyboard vertically for optimal fit (e.g., make the keyboard smaller if there are just two rows of buttons). Defaults to <em>false</em>, in which case the custom keyboard is always of the same height as the app&#39;s standard keyboard.</td>
</tr>
<tr>
<td>one_time_keyboard</td>
<td>Boolean</td>
<td><em>Optional</em>. Requests clients to hide the keyboard as soon as it&#39;s been used. The keyboard will still be available, but clients will automatically display the usual letter-keyboard in the chat – the user can press a special button in the input field to see the custom keyboard again. Defaults to <em>false</em>.</td>
</tr>
<tr>
<td>input_field_placeholder</td>
<td>String</td>
<td><em>Optional</em>. The placeholder to be shown in the input field when the keyboard is active; 1-64 characters</td>
</tr>
<tr>
<td>selective</td>
<td>Boolean</td>
<td><em>Optional</em>. Use this parameter if you want to show the keyboard to specific users only. Targets: 1) users that are @mentioned in the <em>text</em> of the <a href="#message">Message</a> object; 2) if the bot&#39;s message is a reply (has <em>reply_to_message_id</em>), sender of the original message.<br><br><em>Example:</em> A user requests to change the bot&#39;s language, bot replies to the request with a keyboard to select the new language. Other users in the group don&#39;t see the keyboard.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="keyboardbutton" href="#keyboardbutton"><i class="anchor-icon"></i></a>KeyboardButton</h4>
<p>This object represents one button of the reply keyboard. For simple text buttons <em>String</em> can be used instead of this object to specify text of the button. Optional fields <em>request_contact</em>, <em>request_location</em>, and <em>request_poll</em> are mutually exclusive.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>text</td>
<td>String</td>
<td>Text of the button. If none of the optional fields are used, it will be sent as a message when the button is pressed</td>
</tr>
<tr>
<td>request_contact</td>
<td>Boolean</td>
<td><em>Optional</em>. If <em>True</em>, the user&#39;s phone number will be sent as a contact when the button is pressed. Available in private chats only</td>
</tr>
<tr>
<td>request_location</td>
<td>Boolean</td>
<td><em>Optional</em>. If <em>True</em>, the user&#39;s current location will be sent when the button is pressed. Available in private chats only</td>
</tr>
<tr>
<td>request_poll</td>
<td><a href="#keyboardbuttonpolltype">KeyboardButtonPollType</a></td>
<td><em>Optional</em>. If specified, the user will be asked to create a poll and send it to the bot when the button is pressed. Available in private chats only</td>
</tr>
</tbody>
</table>
<p><strong>Note:</strong> <em>request_contact</em> and <em>request_location</em> options will only work in Telegram versions released after 9 April, 2016. Older clients will display <em>unsupported message</em>.<br><strong>Note:</strong> <em>request_poll</em> option will only work in Telegram versions released after 23 January, 2020. Older clients will display <em>unsupported message</em>.</p>
<h4><a class="anchor" name="keyboardbuttonpolltype" href="#keyboardbuttonpolltype"><i class="anchor-icon"></i></a>KeyboardButtonPollType</h4>
<p>This object represents type of a poll, which is allowed to be created and sent when the corresponding button is pressed.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td><em>Optional</em>. If <em>quiz</em> is passed, the user will be allowed to create only polls in the quiz mode. If <em>regular</em> is passed, only regular polls will be allowed. Otherwise, the user will be allowed to create a poll of any type.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="replykeyboardremove" href="#replykeyboardremove"><i class="anchor-icon"></i></a>ReplyKeyboardRemove</h4>
<p>Upon receiving a message with this object, Telegram clients will remove the current custom keyboard and display the default letter-keyboard. By default, custom keyboards are displayed until a new keyboard is sent by a bot. An exception is made for one-time keyboards that are hidden immediately after the user presses a button (see <a href="#replykeyboardmarkup">ReplyKeyboardMarkup</a>).</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>remove_keyboard</td>
<td>True</td>
<td>Requests clients to remove the custom keyboard (user will not be able to summon this keyboard; if you want to hide the keyboard from sight but keep it accessible, use <em>one_time_keyboard</em> in <a href="#replykeyboardmarkup">ReplyKeyboardMarkup</a>)</td>
</tr>
<tr>
<td>selective</td>
<td>Boolean</td>
<td><em>Optional</em>. Use this parameter if you want to remove the keyboard for specific users only. Targets: 1) users that are @mentioned in the <em>text</em> of the <a href="#message">Message</a> object; 2) if the bot&#39;s message is a reply (has <em>reply_to_message_id</em>), sender of the original message.<br><br><em>Example:</em> A user votes in a poll, bot returns confirmation message in reply to the vote and removes the keyboard for that user, while still showing the keyboard with poll options to users who haven&#39;t voted yet.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="inlinekeyboardmarkup" href="#inlinekeyboardmarkup"><i class="anchor-icon"></i></a>InlineKeyboardMarkup</h4>
<p>This object represents an <a href="https://core.telegram.org/bots#inline-keyboards-and-on-the-fly-updating">inline keyboard</a> that appears right next to the message it belongs to.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>inline_keyboard</td>
<td>Array of Array of <a href="#inlinekeyboardbutton">InlineKeyboardButton</a></td>
<td>Array of button rows, each represented by an Array of <a href="#inlinekeyboardbutton">InlineKeyboardButton</a> objects</td>
</tr>
</tbody>
</table>
<p><strong>Note:</strong> This will only work in Telegram versions released after 9 April, 2016. Older clients will display <em>unsupported message</em>.</p>
<h4><a class="anchor" name="inlinekeyboardbutton" href="#inlinekeyboardbutton"><i class="anchor-icon"></i></a>InlineKeyboardButton</h4>
<p>This object represents one button of an inline keyboard. You <strong>must</strong> use exactly one of the optional fields.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>text</td>
<td>String</td>
<td>Label text on the button</td>
</tr>
<tr>
<td>url</td>
<td>String</td>
<td><em>Optional</em>. HTTP or tg:// url to be opened when the button is pressed. Links <code>tg://user?id=&lt;user_id&gt;</code> can be used to mention a user by their ID without using a username, if this is allowed by their privacy settings.</td>
</tr>
<tr>
<td>login_url</td>
<td><a href="#loginurl">LoginUrl</a></td>
<td><em>Optional</em>. An HTTP URL used to automatically authorize the user. Can be used as a replacement for the <a href="https://core.telegram.org/widgets/login">Telegram Login Widget</a>.</td>
</tr>
<tr>
<td>callback_data</td>
<td>String</td>
<td><em>Optional</em>. Data to be sent in a <a href="#callbackquery">callback query</a> to the bot when button is pressed, 1-64 bytes</td>
</tr>
<tr>
<td>switch_inline_query</td>
<td>String</td>
<td><em>Optional</em>. If set, pressing the button will prompt the user to select one of their chats, open that chat and insert the bot&#39;s username and the specified inline query in the input field. Can be empty, in which case just the bot&#39;s username will be inserted.<br><br><strong>Note:</strong> This offers an easy way for users to start using your bot in <a href="/bots/inline">inline mode</a> when they are currently in a private chat with it. Especially useful when combined with <a href="#answerinlinequery"><em>switch_pm…</em></a> actions – in this case the user will be automatically returned to the chat they switched from, skipping the chat selection screen.</td>
</tr>
<tr>
<td>switch_inline_query_current_chat</td>
<td>String</td>
<td><em>Optional</em>. If set, pressing the button will insert the bot&#39;s username and the specified inline query in the current chat&#39;s input field. Can be empty, in which case only the bot&#39;s username will be inserted.<br><br>This offers a quick way for the user to open your bot in inline mode in the same chat – good for selecting something from multiple options.</td>
</tr>
<tr>
<td>callback_game</td>
<td><a href="#callbackgame">CallbackGame</a></td>
<td><em>Optional</em>. Description of the game that will be launched when the user presses the button.<br><br><strong>NOTE:</strong> This type of button <strong>must</strong> always be the first button in the first row.</td>
</tr>
<tr>
<td>pay</td>
<td>Boolean</td>
<td><em>Optional</em>. Specify <em>True</em>, to send a <a href="#payments">Pay button</a>.<br><br><strong>NOTE:</strong> This type of button <strong>must</strong> always be the first button in the first row and can only be used in invoice messages.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="loginurl" href="#loginurl"><i class="anchor-icon"></i></a>LoginUrl</h4>
<p>This object represents a parameter of the inline keyboard button used to automatically authorize a user. Serves as a great replacement for the <a href="https://core.telegram.org/widgets/login">Telegram Login Widget</a> when the user is coming from Telegram. All the user needs to do is tap/click a button and confirm that they want to log in:</p>
<div class="blog_image_wrap">
  <a href="/file/811140015/1734/8VZFkwWXalM.97872/6127fa62d8a0bf2b3c" target="_blank"><img src="/file/811140909/1631/20k1Z53eiyY.23995/c541e89b74253623d9" title="TITLE" alt="TITLE" srcset="/file/811140015/1734/8VZFkwWXalM.97872/6127fa62d8a0bf2b3c , 2x" /></a>
</div>

<p>Telegram apps support these buttons as of <a href="https://telegram.org/blog/privacy-discussions-web-bots#meet-seamless-web-bots">version 5.7</a>.</p>
<blockquote>
<p>Sample bot: <a href="https://t.me/discussbot">@discussbot</a></p>
</blockquote>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>url</td>
<td>String</td>
<td>An HTTP URL to be opened with user authorization data added to the query string when the button is pressed. If the user refuses to provide authorization data, the original URL without information about the user will be opened. The data added is the same as described in <a href="https://core.telegram.org/widgets/login#receiving-authorization-data">Receiving authorization data</a>.<br><br><strong>NOTE:</strong> You <strong>must</strong> always check the hash of the received data to verify the authentication and the integrity of the data as described in <a href="https://core.telegram.org/widgets/login#checking-authorization">Checking authorization</a>.</td>
</tr>
<tr>
<td>forward_text</td>
<td>String</td>
<td><em>Optional</em>. New text of the button in forwarded messages.</td>
</tr>
<tr>
<td>bot_username</td>
<td>String</td>
<td><em>Optional</em>. Username of a bot, which will be used for user authorization. See <a href="https://core.telegram.org/widgets/login#setting-up-a-bot">Setting up a bot</a> for more details. If not specified, the current bot&#39;s username will be assumed. The <em>url</em>&#39;s domain must be the same as the domain linked with the bot. See <a href="https://core.telegram.org/widgets/login#linking-your-domain-to-the-bot">Linking your domain to the bot</a> for more details.</td>
</tr>
<tr>
<td>request_write_access</td>
<td>Boolean</td>
<td><em>Optional</em>. Pass <em>True</em> to request the permission for your bot to send messages to the user.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="callbackquery" href="#callbackquery"><i class="anchor-icon"></i></a>CallbackQuery</h4>
<p>This object represents an incoming callback query from a callback button in an <a href="/bots#inline-keyboards-and-on-the-fly-updating">inline keyboard</a>. If the button that originated the query was attached to a message sent by the bot, the field <em>message</em> will be present. If the button was attached to a message sent via the bot (in <a href="#inline-mode">inline mode</a>), the field <em>inline_message_id</em> will be present. Exactly one of the fields <em>data</em> or <em>game_short_name</em> will be present.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>id</td>
<td>String</td>
<td>Unique identifier for this query</td>
</tr>
<tr>
<td>from</td>
<td><a href="#user">User</a></td>
<td>Sender</td>
</tr>
<tr>
<td>message</td>
<td><a href="#message">Message</a></td>
<td><em>Optional</em>. Message with the callback button that originated the query. Note that message content and message date will not be available if the message is too old</td>
</tr>
<tr>
<td>inline_message_id</td>
<td>String</td>
<td><em>Optional</em>. Identifier of the message sent via the bot in inline mode, that originated the query.</td>
</tr>
<tr>
<td>chat_instance</td>
<td>String</td>
<td>Global identifier, uniquely corresponding to the chat to which the message with the callback button was sent. Useful for high scores in <a href="#games">games</a>.</td>
</tr>
<tr>
<td>data</td>
<td>String</td>
<td><em>Optional</em>. Data associated with the callback button. Be aware that a bad client can send arbitrary data in this field.</td>
</tr>
<tr>
<td>game_short_name</td>
<td>String</td>
<td><em>Optional</em>. Short name of a <a href="#games">Game</a> to be returned, serves as the unique identifier for the game</td>
</tr>
</tbody>
</table>
<blockquote>
<p><strong>NOTE:</strong> After the user presses a callback button, Telegram clients will display a progress bar until you call <a href="#answercallbackquery">answerCallbackQuery</a>. It is, therefore, necessary to react by calling <a href="#answercallbackquery">answerCallbackQuery</a> even if no notification to the user is needed (e.g., without specifying any of the optional parameters).</p>
</blockquote>
<h4><a class="anchor" name="forcereply" href="#forcereply"><i class="anchor-icon"></i></a>ForceReply</h4>
<p>Upon receiving a message with this object, Telegram clients will display a reply interface to the user (act as if the user has selected the bot&#39;s message and tapped &#39;Reply&#39;). This can be extremely useful if you want to create user-friendly step-by-step interfaces without having to sacrifice <a href="/bots#privacy-mode">privacy mode</a>.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>force_reply</td>
<td>True</td>
<td>Shows reply interface to the user, as if they manually selected the bot&#39;s message and tapped &#39;Reply&#39;</td>
</tr>
<tr>
<td>input_field_placeholder</td>
<td>String</td>
<td><em>Optional</em>. The placeholder to be shown in the input field when the reply is active; 1-64 characters</td>
</tr>
<tr>
<td>selective</td>
<td>Boolean</td>
<td><em>Optional</em>. Use this parameter if you want to force reply from specific users only. Targets: 1) users that are @mentioned in the <em>text</em> of the <a href="#message">Message</a> object; 2) if the bot&#39;s message is a reply (has <em>reply_to_message_id</em>), sender of the original message.</td>
</tr>
</tbody>
</table>
<blockquote>
<p><strong>Example:</strong> A <a href="https://t.me/PollBot">poll bot</a> for groups runs in privacy mode (only receives commands, replies to its messages and mentions). There could be two ways to create a new poll:</p>
<ul>
<li>Explain the user how to send a command with parameters (e.g. /newpoll question answer1 answer2). May be appealing for hardcore users but lacks modern day polish.</li>
<li>Guide the user through a step-by-step process. &#39;Please send me your question&#39;, &#39;Cool, now let&#39;s add the first answer option&#39;, &#39;Great. Keep adding answer options, then send /done when you&#39;re ready&#39;.</li>
</ul>
<p>The last option is definitely more attractive. And if you use <a href="#forcereply">ForceReply</a> in your bot&#39;s questions, it will receive the user&#39;s answers even if it only receives replies, commands and mentions — without any extra work for the user.</p>
</blockquote>
<h4><a class="anchor" name="chatphoto" href="#chatphoto"><i class="anchor-icon"></i></a>ChatPhoto</h4>
<p>This object represents a chat photo.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>small_file_id</td>
<td>String</td>
<td>File identifier of small (160x160) chat photo. This file_id can be used only for photo download and only for as long as the photo is not changed.</td>
</tr>
<tr>
<td>small_file_unique_id</td>
<td>String</td>
<td>Unique file identifier of small (160x160) chat photo, which is supposed to be the same over time and for different bots. Can&#39;t be used to download or reuse the file.</td>
</tr>
<tr>
<td>big_file_id</td>
<td>String</td>
<td>File identifier of big (640x640) chat photo. This file_id can be used only for photo download and only for as long as the photo is not changed.</td>
</tr>
<tr>
<td>big_file_unique_id</td>
<td>String</td>
<td>Unique file identifier of big (640x640) chat photo, which is supposed to be the same over time and for different bots. Can&#39;t be used to download or reuse the file.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="chatinvitelink" href="#chatinvitelink"><i class="anchor-icon"></i></a>ChatInviteLink</h4>
<p>Represents an invite link for a chat.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>invite_link</td>
<td>String</td>
<td>The invite link. If the link was created by another chat administrator, then the second part of the link will be replaced with “…”.</td>
</tr>
<tr>
<td>creator</td>
<td><a href="#user">User</a></td>
<td>Creator of the link</td>
</tr>
<tr>
<td>creates_join_request</td>
<td>Boolean</td>
<td><em>True</em>, if users joining the chat via the link need to be approved by chat administrators</td>
</tr>
<tr>
<td>is_primary</td>
<td>Boolean</td>
<td><em>True</em>, if the link is primary</td>
</tr>
<tr>
<td>is_revoked</td>
<td>Boolean</td>
<td><em>True</em>, if the link is revoked</td>
</tr>
<tr>
<td>name</td>
<td>String</td>
<td><em>Optional</em>. Invite link name</td>
</tr>
<tr>
<td>expire_date</td>
<td>Integer</td>
<td><em>Optional</em>. Point in time (Unix timestamp) when the link will expire or has been expired</td>
</tr>
<tr>
<td>member_limit</td>
<td>Integer</td>
<td><em>Optional</em>. Maximum number of users that can be members of the chat simultaneously after joining the chat via this invite link; 1-99999</td>
</tr>
<tr>
<td>pending_join_request_count</td>
<td>Integer</td>
<td><em>Optional</em>. Number of pending join requests created using this link</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="chatmember" href="#chatmember"><i class="anchor-icon"></i></a>ChatMember</h4>
<p>This object contains information about one member of a chat. Currently, the following 6 types of chat members are supported:</p>
<ul>
<li><a href="#chatmemberowner">ChatMemberOwner</a></li>
<li><a href="#chatmemberadministrator">ChatMemberAdministrator</a></li>
<li><a href="#chatmembermember">ChatMemberMember</a></li>
<li><a href="#chatmemberrestricted">ChatMemberRestricted</a></li>
<li><a href="#chatmemberleft">ChatMemberLeft</a></li>
<li><a href="#chatmemberbanned">ChatMemberBanned</a></li>
</ul>
<h4><a class="anchor" name="chatmemberowner" href="#chatmemberowner"><i class="anchor-icon"></i></a>ChatMemberOwner</h4>
<p>Represents a <a href="#chatmember">chat member</a> that owns the chat and has all administrator privileges.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>status</td>
<td>String</td>
<td>The member&#39;s status in the chat, always “creator”</td>
</tr>
<tr>
<td>user</td>
<td><a href="#user">User</a></td>
<td>Information about the user</td>
</tr>
<tr>
<td>is_anonymous</td>
<td>Boolean</td>
<td><em>True</em>, if the user&#39;s presence in the chat is hidden</td>
</tr>
<tr>
<td>custom_title</td>
<td>String</td>
<td><em>Optional</em>. Custom title for this user</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="chatmemberadministrator" href="#chatmemberadministrator"><i class="anchor-icon"></i></a>ChatMemberAdministrator</h4>
<p>Represents a <a href="#chatmember">chat member</a> that has some additional privileges.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>status</td>
<td>String</td>
<td>The member&#39;s status in the chat, always “administrator”</td>
</tr>
<tr>
<td>user</td>
<td><a href="#user">User</a></td>
<td>Information about the user</td>
</tr>
<tr>
<td>can_be_edited</td>
<td>Boolean</td>
<td><em>True</em>, if the bot is allowed to edit administrator privileges of that user</td>
</tr>
<tr>
<td>is_anonymous</td>
<td>Boolean</td>
<td><em>True</em>, if the user&#39;s presence in the chat is hidden</td>
</tr>
<tr>
<td>can_manage_chat</td>
<td>Boolean</td>
<td><em>True</em>, if the administrator can access the chat event log, chat statistics, message statistics in channels, see channel members, see anonymous administrators in supergroups and ignore slow mode. Implied by any other administrator privilege</td>
</tr>
<tr>
<td>can_delete_messages</td>
<td>Boolean</td>
<td><em>True</em>, if the administrator can delete messages of other users</td>
</tr>
<tr>
<td>can_manage_voice_chats</td>
<td>Boolean</td>
<td><em>True</em>, if the administrator can manage voice chats</td>
</tr>
<tr>
<td>can_restrict_members</td>
<td>Boolean</td>
<td><em>True</em>, if the administrator can restrict, ban or unban chat members</td>
</tr>
<tr>
<td>can_promote_members</td>
<td>Boolean</td>
<td><em>True</em>, if the administrator can add new administrators with a subset of their own privileges or demote administrators that he has promoted, directly or indirectly (promoted by administrators that were appointed by the user)</td>
</tr>
<tr>
<td>can_change_info</td>
<td>Boolean</td>
<td><em>True</em>, if the user is allowed to change the chat title, photo and other settings</td>
</tr>
<tr>
<td>can_invite_users</td>
<td>Boolean</td>
<td><em>True</em>, if the user is allowed to invite new users to the chat</td>
</tr>
<tr>
<td>can_post_messages</td>
<td>Boolean</td>
<td><em>Optional</em>. <em>True</em>, if the administrator can post in the channel; channels only</td>
</tr>
<tr>
<td>can_edit_messages</td>
<td>Boolean</td>
<td><em>Optional</em>. <em>True</em>, if the administrator can edit messages of other users and can pin messages; channels only</td>
</tr>
<tr>
<td>can_pin_messages</td>
<td>Boolean</td>
<td><em>Optional</em>. <em>True</em>, if the user is allowed to pin messages; groups and supergroups only</td>
</tr>
<tr>
<td>custom_title</td>
<td>String</td>
<td><em>Optional</em>. Custom title for this user</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="chatmembermember" href="#chatmembermember"><i class="anchor-icon"></i></a>ChatMemberMember</h4>
<p>Represents a <a href="#chatmember">chat member</a> that has no additional privileges or restrictions.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>status</td>
<td>String</td>
<td>The member&#39;s status in the chat, always “member”</td>
</tr>
<tr>
<td>user</td>
<td><a href="#user">User</a></td>
<td>Information about the user</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="chatmemberrestricted" href="#chatmemberrestricted"><i class="anchor-icon"></i></a>ChatMemberRestricted</h4>
<p>Represents a <a href="#chatmember">chat member</a> that is under certain restrictions in the chat. Supergroups only.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>status</td>
<td>String</td>
<td>The member&#39;s status in the chat, always “restricted”</td>
</tr>
<tr>
<td>user</td>
<td><a href="#user">User</a></td>
<td>Information about the user</td>
</tr>
<tr>
<td>is_member</td>
<td>Boolean</td>
<td><em>True</em>, if the user is a member of the chat at the moment of the request</td>
</tr>
<tr>
<td>can_change_info</td>
<td>Boolean</td>
<td><em>True</em>, if the user is allowed to change the chat title, photo and other settings</td>
</tr>
<tr>
<td>can_invite_users</td>
<td>Boolean</td>
<td><em>True</em>, if the user is allowed to invite new users to the chat</td>
</tr>
<tr>
<td>can_pin_messages</td>
<td>Boolean</td>
<td><em>True</em>, if the user is allowed to pin messages</td>
</tr>
<tr>
<td>can_send_messages</td>
<td>Boolean</td>
<td><em>True</em>, if the user is allowed to send text messages, contacts, locations and venues</td>
</tr>
<tr>
<td>can_send_media_messages</td>
<td>Boolean</td>
<td><em>True</em>, if the user is allowed to send audios, documents, photos, videos, video notes and voice notes</td>
</tr>
<tr>
<td>can_send_polls</td>
<td>Boolean</td>
<td><em>True</em>, if the user is allowed to send polls</td>
</tr>
<tr>
<td>can_send_other_messages</td>
<td>Boolean</td>
<td><em>True</em>, if the user is allowed to send animations, games, stickers and use inline bots</td>
</tr>
<tr>
<td>can_add_web_page_previews</td>
<td>Boolean</td>
<td><em>True</em>, if the user is allowed to add web page previews to their messages</td>
</tr>
<tr>
<td>until_date</td>
<td>Integer</td>
<td>Date when restrictions will be lifted for this user; unix time. If 0, then the user is restricted forever</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="chatmemberleft" href="#chatmemberleft"><i class="anchor-icon"></i></a>ChatMemberLeft</h4>
<p>Represents a <a href="#chatmember">chat member</a> that isn&#39;t currently a member of the chat, but may join it themselves.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>status</td>
<td>String</td>
<td>The member&#39;s status in the chat, always “left”</td>
</tr>
<tr>
<td>user</td>
<td><a href="#user">User</a></td>
<td>Information about the user</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="chatmemberbanned" href="#chatmemberbanned"><i class="anchor-icon"></i></a>ChatMemberBanned</h4>
<p>Represents a <a href="#chatmember">chat member</a> that was banned in the chat and can&#39;t return to the chat or view chat messages.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>status</td>
<td>String</td>
<td>The member&#39;s status in the chat, always “kicked”</td>
</tr>
<tr>
<td>user</td>
<td><a href="#user">User</a></td>
<td>Information about the user</td>
</tr>
<tr>
<td>until_date</td>
<td>Integer</td>
<td>Date when restrictions will be lifted for this user; unix time. If 0, then the user is banned forever</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="chatmemberupdated" href="#chatmemberupdated"><i class="anchor-icon"></i></a>ChatMemberUpdated</h4>
<p>This object represents changes in the status of a chat member.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat</td>
<td><a href="#chat">Chat</a></td>
<td>Chat the user belongs to</td>
</tr>
<tr>
<td>from</td>
<td><a href="#user">User</a></td>
<td>Performer of the action, which resulted in the change</td>
</tr>
<tr>
<td>date</td>
<td>Integer</td>
<td>Date the change was done in Unix time</td>
</tr>
<tr>
<td>old_chat_member</td>
<td><a href="#chatmember">ChatMember</a></td>
<td>Previous information about the chat member</td>
</tr>
<tr>
<td>new_chat_member</td>
<td><a href="#chatmember">ChatMember</a></td>
<td>New information about the chat member</td>
</tr>
<tr>
<td>invite_link</td>
<td><a href="#chatinvitelink">ChatInviteLink</a></td>
<td><em>Optional</em>. Chat invite link, which was used by the user to join the chat; for joining by invite link events only.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="chatjoinrequest" href="#chatjoinrequest"><i class="anchor-icon"></i></a>ChatJoinRequest</h4>
<p>Represents a join request sent to a chat.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat</td>
<td><a href="#chat">Chat</a></td>
<td>Chat to which the request was sent</td>
</tr>
<tr>
<td>from</td>
<td><a href="#user">User</a></td>
<td>User that sent the join request</td>
</tr>
<tr>
<td>date</td>
<td>Integer</td>
<td>Date the request was sent in Unix time</td>
</tr>
<tr>
<td>bio</td>
<td>String</td>
<td><em>Optional</em>. Bio of the user.</td>
</tr>
<tr>
<td>invite_link</td>
<td><a href="#chatinvitelink">ChatInviteLink</a></td>
<td><em>Optional</em>. Chat invite link that was used by the user to send the join request</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="chatpermissions" href="#chatpermissions"><i class="anchor-icon"></i></a>ChatPermissions</h4>
<p>Describes actions that a non-administrator user is allowed to take in a chat.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>can_send_messages</td>
<td>Boolean</td>
<td><em>Optional</em>. <em>True</em>, if the user is allowed to send text messages, contacts, locations and venues</td>
</tr>
<tr>
<td>can_send_media_messages</td>
<td>Boolean</td>
<td><em>Optional</em>. <em>True</em>, if the user is allowed to send audios, documents, photos, videos, video notes and voice notes, implies can_send_messages</td>
</tr>
<tr>
<td>can_send_polls</td>
<td>Boolean</td>
<td><em>Optional</em>. <em>True</em>, if the user is allowed to send polls, implies can_send_messages</td>
</tr>
<tr>
<td>can_send_other_messages</td>
<td>Boolean</td>
<td><em>Optional</em>. <em>True</em>, if the user is allowed to send animations, games, stickers and use inline bots, implies can_send_media_messages</td>
</tr>
<tr>
<td>can_add_web_page_previews</td>
<td>Boolean</td>
<td><em>Optional</em>. <em>True</em>, if the user is allowed to add web page previews to their messages, implies can_send_media_messages</td>
</tr>
<tr>
<td>can_change_info</td>
<td>Boolean</td>
<td><em>Optional</em>. <em>True</em>, if the user is allowed to change the chat title, photo and other settings. Ignored in public supergroups</td>
</tr>
<tr>
<td>can_invite_users</td>
<td>Boolean</td>
<td><em>Optional</em>. <em>True</em>, if the user is allowed to invite new users to the chat</td>
</tr>
<tr>
<td>can_pin_messages</td>
<td>Boolean</td>
<td><em>Optional</em>. <em>True</em>, if the user is allowed to pin messages. Ignored in public supergroups</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="chatlocation" href="#chatlocation"><i class="anchor-icon"></i></a>ChatLocation</h4>
<p>Represents a location to which a chat is connected.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>location</td>
<td><a href="#location">Location</a></td>
<td>The location to which the supergroup is connected. Can&#39;t be a live location.</td>
</tr>
<tr>
<td>address</td>
<td>String</td>
<td>Location address; 1-64 characters, as defined by the chat owner</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="botcommand" href="#botcommand"><i class="anchor-icon"></i></a>BotCommand</h4>
<p>This object represents a bot command.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>command</td>
<td>String</td>
<td>Text of the command; 1-32 characters. Can contain only lowercase English letters, digits and underscores.</td>
</tr>
<tr>
<td>description</td>
<td>String</td>
<td>Description of the command; 1-256 characters.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="botcommandscope" href="#botcommandscope"><i class="anchor-icon"></i></a>BotCommandScope</h4>
<p>This object represents the scope to which bot commands are applied. Currently, the following 7 scopes are supported:</p>
<ul>
<li><a href="#botcommandscopedefault">BotCommandScopeDefault</a></li>
<li><a href="#botcommandscopeallprivatechats">BotCommandScopeAllPrivateChats</a></li>
<li><a href="#botcommandscopeallgroupchats">BotCommandScopeAllGroupChats</a></li>
<li><a href="#botcommandscopeallchatadministrators">BotCommandScopeAllChatAdministrators</a></li>
<li><a href="#botcommandscopechat">BotCommandScopeChat</a></li>
<li><a href="#botcommandscopechatadministrators">BotCommandScopeChatAdministrators</a></li>
<li><a href="#botcommandscopechatmember">BotCommandScopeChatMember</a></li>
</ul>
<h4><a class="anchor" name="determining-list-of-commands" href="#determining-list-of-commands"><i class="anchor-icon"></i></a>Determining list of commands</h4>
<p>The following algorithm is used to determine the list of commands for a particular user viewing the bot menu. The first list of commands which is set is returned:</p>
<p><strong>Commands in the chat with the bot</strong></p>
<ul>
<li>botCommandScopeChat + language_code</li>
<li>botCommandScopeChat</li>
<li>botCommandScopeAllPrivateChats + language_code</li>
<li>botCommandScopeAllPrivateChats</li>
<li>botCommandScopeDefault + language_code</li>
<li>botCommandScopeDefault</li>
</ul>
<p><strong>Commands in group and supergroup chats</strong></p>
<ul>
<li>botCommandScopeChatMember + language_code</li>
<li>botCommandScopeChatMember</li>
<li>botCommandScopeChatAdministrators + language_code (administrators only)</li>
<li>botCommandScopeChatAdministrators (administrators only)</li>
<li>botCommandScopeChat + language_code</li>
<li>botCommandScopeChat</li>
<li>botCommandScopeAllChatAdministrators + language_code (administrators only)</li>
<li>botCommandScopeAllChatAdministrators (administrators only)</li>
<li>botCommandScopeAllGroupChats + language_code</li>
<li>botCommandScopeAllGroupChats</li>
<li>botCommandScopeDefault + language_code</li>
<li>botCommandScopeDefault</li>
</ul>
<h4><a class="anchor" name="botcommandscopedefault" href="#botcommandscopedefault"><i class="anchor-icon"></i></a>BotCommandScopeDefault</h4>
<p>Represents the default <a href="#botcommandscope">scope</a> of bot commands. Default commands are used if no commands with a <a href="#determining-list-of-commands">narrower scope</a> are specified for the user.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Scope type, must be <em>default</em></td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="botcommandscopeallprivatechats" href="#botcommandscopeallprivatechats"><i class="anchor-icon"></i></a>BotCommandScopeAllPrivateChats</h4>
<p>Represents the <a href="#botcommandscope">scope</a> of bot commands, covering all private chats.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Scope type, must be <em>all_private_chats</em></td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="botcommandscopeallgroupchats" href="#botcommandscopeallgroupchats"><i class="anchor-icon"></i></a>BotCommandScopeAllGroupChats</h4>
<p>Represents the <a href="#botcommandscope">scope</a> of bot commands, covering all group and supergroup chats.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Scope type, must be <em>all_group_chats</em></td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="botcommandscopeallchatadministrators" href="#botcommandscopeallchatadministrators"><i class="anchor-icon"></i></a>BotCommandScopeAllChatAdministrators</h4>
<p>Represents the <a href="#botcommandscope">scope</a> of bot commands, covering all group and supergroup chat administrators.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Scope type, must be <em>all_chat_administrators</em></td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="botcommandscopechat" href="#botcommandscopechat"><i class="anchor-icon"></i></a>BotCommandScopeChat</h4>
<p>Represents the <a href="#botcommandscope">scope</a> of bot commands, covering a specific chat.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Scope type, must be <em>chat</em></td>
</tr>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Unique identifier for the target chat or username of the target supergroup (in the format <code>@supergroupusername</code>)</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="botcommandscopechatadministrators" href="#botcommandscopechatadministrators"><i class="anchor-icon"></i></a>BotCommandScopeChatAdministrators</h4>
<p>Represents the <a href="#botcommandscope">scope</a> of bot commands, covering all administrators of a specific group or supergroup chat.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Scope type, must be <em>chat_administrators</em></td>
</tr>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Unique identifier for the target chat or username of the target supergroup (in the format <code>@supergroupusername</code>)</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="botcommandscopechatmember" href="#botcommandscopechatmember"><i class="anchor-icon"></i></a>BotCommandScopeChatMember</h4>
<p>Represents the <a href="#botcommandscope">scope</a> of bot commands, covering a specific member of a group or supergroup chat.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Scope type, must be <em>chat_member</em></td>
</tr>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Unique identifier for the target chat or username of the target supergroup (in the format <code>@supergroupusername</code>)</td>
</tr>
<tr>
<td>user_id</td>
<td>Integer</td>
<td>Unique identifier of the target user</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="responseparameters" href="#responseparameters"><i class="anchor-icon"></i></a>ResponseParameters</h4>
<p>Contains information about why a request was unsuccessful.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>migrate_to_chat_id</td>
<td>Integer</td>
<td><em>Optional</em>. The group has been migrated to a supergroup with the specified identifier. This number may have more than 32 significant bits and some programming languages may have difficulty/silent defects in interpreting it. But it has at most 52 significant bits, so a signed 64-bit integer or double-precision float type are safe for storing this identifier.</td>
</tr>
<tr>
<td>retry_after</td>
<td>Integer</td>
<td><em>Optional</em>. In case of exceeding flood control, the number of seconds left to wait before the request can be repeated</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="inputmedia" href="#inputmedia"><i class="anchor-icon"></i></a>InputMedia</h4>
<p>This object represents the content of a media message to be sent. It should be one of</p>
<ul>
<li><a href="#inputmediaanimation">InputMediaAnimation</a></li>
<li><a href="#inputmediadocument">InputMediaDocument</a></li>
<li><a href="#inputmediaaudio">InputMediaAudio</a></li>
<li><a href="#inputmediaphoto">InputMediaPhoto</a></li>
<li><a href="#inputmediavideo">InputMediaVideo</a></li>
</ul>
<h4><a class="anchor" name="inputmediaphoto" href="#inputmediaphoto"><i class="anchor-icon"></i></a>InputMediaPhoto</h4>
<p>Represents a photo to be sent.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Type of the result, must be <em>photo</em></td>
</tr>
<tr>
<td>media</td>
<td>String</td>
<td>File to send. Pass a file_id to send a file that exists on the Telegram servers (recommended), pass an HTTP URL for Telegram to get a file from the Internet, or pass “attach://&lt;file_attach_name&gt;” to upload a new one using multipart/form-data under &lt;file_attach_name&gt; name. <a href="#sending-files">More info on Sending Files »</a></td>
</tr>
<tr>
<td>caption</td>
<td>String</td>
<td><em>Optional</em>. Caption of the photo to be sent, 0-1024 characters after entities parsing</td>
</tr>
<tr>
<td>parse_mode</td>
<td>String</td>
<td><em>Optional</em>. Mode for parsing entities in the photo caption. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>caption_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td><em>Optional</em>. List of special entities that appear in the caption, which can be specified instead of <em>parse_mode</em></td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="inputmediavideo" href="#inputmediavideo"><i class="anchor-icon"></i></a>InputMediaVideo</h4>
<p>Represents a video to be sent.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Type of the result, must be <em>video</em></td>
</tr>
<tr>
<td>media</td>
<td>String</td>
<td>File to send. Pass a file_id to send a file that exists on the Telegram servers (recommended), pass an HTTP URL for Telegram to get a file from the Internet, or pass “attach://&lt;file_attach_name&gt;” to upload a new one using multipart/form-data under &lt;file_attach_name&gt; name. <a href="#sending-files">More info on Sending Files »</a></td>
</tr>
<tr>
<td>thumb</td>
<td><a href="#inputfile">InputFile</a> or String</td>
<td><em>Optional</em>. Thumbnail of the file sent; can be ignored if thumbnail generation for the file is supported server-side. The thumbnail should be in JPEG format and less than 200 kB in size. A thumbnail&#39;s width and height should not exceed 320. Ignored if the file is not uploaded using multipart/form-data. Thumbnails can&#39;t be reused and can be only uploaded as a new file, so you can pass “attach://&lt;file_attach_name&gt;” if the thumbnail was uploaded using multipart/form-data under &lt;file_attach_name&gt;. <a href="#sending-files">More info on Sending Files »</a></td>
</tr>
<tr>
<td>caption</td>
<td>String</td>
<td><em>Optional</em>. Caption of the video to be sent, 0-1024 characters after entities parsing</td>
</tr>
<tr>
<td>parse_mode</td>
<td>String</td>
<td><em>Optional</em>. Mode for parsing entities in the video caption. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>caption_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td><em>Optional</em>. List of special entities that appear in the caption, which can be specified instead of <em>parse_mode</em></td>
</tr>
<tr>
<td>width</td>
<td>Integer</td>
<td><em>Optional</em>. Video width</td>
</tr>
<tr>
<td>height</td>
<td>Integer</td>
<td><em>Optional</em>. Video height</td>
</tr>
<tr>
<td>duration</td>
<td>Integer</td>
<td><em>Optional</em>. Video duration in seconds</td>
</tr>
<tr>
<td>supports_streaming</td>
<td>Boolean</td>
<td><em>Optional</em>. Pass <em>True</em>, if the uploaded video is suitable for streaming</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="inputmediaanimation" href="#inputmediaanimation"><i class="anchor-icon"></i></a>InputMediaAnimation</h4>
<p>Represents an animation file (GIF or H.264/MPEG-4 AVC video without sound) to be sent.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Type of the result, must be <em>animation</em></td>
</tr>
<tr>
<td>media</td>
<td>String</td>
<td>File to send. Pass a file_id to send a file that exists on the Telegram servers (recommended), pass an HTTP URL for Telegram to get a file from the Internet, or pass “attach://&lt;file_attach_name&gt;” to upload a new one using multipart/form-data under &lt;file_attach_name&gt; name. <a href="#sending-files">More info on Sending Files »</a></td>
</tr>
<tr>
<td>thumb</td>
<td><a href="#inputfile">InputFile</a> or String</td>
<td><em>Optional</em>. Thumbnail of the file sent; can be ignored if thumbnail generation for the file is supported server-side. The thumbnail should be in JPEG format and less than 200 kB in size. A thumbnail&#39;s width and height should not exceed 320. Ignored if the file is not uploaded using multipart/form-data. Thumbnails can&#39;t be reused and can be only uploaded as a new file, so you can pass “attach://&lt;file_attach_name&gt;” if the thumbnail was uploaded using multipart/form-data under &lt;file_attach_name&gt;. <a href="#sending-files">More info on Sending Files »</a></td>
</tr>
<tr>
<td>caption</td>
<td>String</td>
<td><em>Optional</em>. Caption of the animation to be sent, 0-1024 characters after entities parsing</td>
</tr>
<tr>
<td>parse_mode</td>
<td>String</td>
<td><em>Optional</em>. Mode for parsing entities in the animation caption. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>caption_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td><em>Optional</em>. List of special entities that appear in the caption, which can be specified instead of <em>parse_mode</em></td>
</tr>
<tr>
<td>width</td>
<td>Integer</td>
<td><em>Optional</em>. Animation width</td>
</tr>
<tr>
<td>height</td>
<td>Integer</td>
<td><em>Optional</em>. Animation height</td>
</tr>
<tr>
<td>duration</td>
<td>Integer</td>
<td><em>Optional</em>. Animation duration in seconds</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="inputmediaaudio" href="#inputmediaaudio"><i class="anchor-icon"></i></a>InputMediaAudio</h4>
<p>Represents an audio file to be treated as music to be sent.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Type of the result, must be <em>audio</em></td>
</tr>
<tr>
<td>media</td>
<td>String</td>
<td>File to send. Pass a file_id to send a file that exists on the Telegram servers (recommended), pass an HTTP URL for Telegram to get a file from the Internet, or pass “attach://&lt;file_attach_name&gt;” to upload a new one using multipart/form-data under &lt;file_attach_name&gt; name. <a href="#sending-files">More info on Sending Files »</a></td>
</tr>
<tr>
<td>thumb</td>
<td><a href="#inputfile">InputFile</a> or String</td>
<td><em>Optional</em>. Thumbnail of the file sent; can be ignored if thumbnail generation for the file is supported server-side. The thumbnail should be in JPEG format and less than 200 kB in size. A thumbnail&#39;s width and height should not exceed 320. Ignored if the file is not uploaded using multipart/form-data. Thumbnails can&#39;t be reused and can be only uploaded as a new file, so you can pass “attach://&lt;file_attach_name&gt;” if the thumbnail was uploaded using multipart/form-data under &lt;file_attach_name&gt;. <a href="#sending-files">More info on Sending Files »</a></td>
</tr>
<tr>
<td>caption</td>
<td>String</td>
<td><em>Optional</em>. Caption of the audio to be sent, 0-1024 characters after entities parsing</td>
</tr>
<tr>
<td>parse_mode</td>
<td>String</td>
<td><em>Optional</em>. Mode for parsing entities in the audio caption. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>caption_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td><em>Optional</em>. List of special entities that appear in the caption, which can be specified instead of <em>parse_mode</em></td>
</tr>
<tr>
<td>duration</td>
<td>Integer</td>
<td><em>Optional</em>. Duration of the audio in seconds</td>
</tr>
<tr>
<td>performer</td>
<td>String</td>
<td><em>Optional</em>. Performer of the audio</td>
</tr>
<tr>
<td>title</td>
<td>String</td>
<td><em>Optional</em>. Title of the audio</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="inputmediadocument" href="#inputmediadocument"><i class="anchor-icon"></i></a>InputMediaDocument</h4>
<p>Represents a general file to be sent.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Type of the result, must be <em>document</em></td>
</tr>
<tr>
<td>media</td>
<td>String</td>
<td>File to send. Pass a file_id to send a file that exists on the Telegram servers (recommended), pass an HTTP URL for Telegram to get a file from the Internet, or pass “attach://&lt;file_attach_name&gt;” to upload a new one using multipart/form-data under &lt;file_attach_name&gt; name. <a href="#sending-files">More info on Sending Files »</a></td>
</tr>
<tr>
<td>thumb</td>
<td><a href="#inputfile">InputFile</a> or String</td>
<td><em>Optional</em>. Thumbnail of the file sent; can be ignored if thumbnail generation for the file is supported server-side. The thumbnail should be in JPEG format and less than 200 kB in size. A thumbnail&#39;s width and height should not exceed 320. Ignored if the file is not uploaded using multipart/form-data. Thumbnails can&#39;t be reused and can be only uploaded as a new file, so you can pass “attach://&lt;file_attach_name&gt;” if the thumbnail was uploaded using multipart/form-data under &lt;file_attach_name&gt;. <a href="#sending-files">More info on Sending Files »</a></td>
</tr>
<tr>
<td>caption</td>
<td>String</td>
<td><em>Optional</em>. Caption of the document to be sent, 0-1024 characters after entities parsing</td>
</tr>
<tr>
<td>parse_mode</td>
<td>String</td>
<td><em>Optional</em>. Mode for parsing entities in the document caption. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>caption_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td><em>Optional</em>. List of special entities that appear in the caption, which can be specified instead of <em>parse_mode</em></td>
</tr>
<tr>
<td>disable_content_type_detection</td>
<td>Boolean</td>
<td><em>Optional</em>. Disables automatic server-side content type detection for files uploaded using multipart/form-data. Always <em>True</em>, if the document is sent as part of an album.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="inputfile" href="#inputfile"><i class="anchor-icon"></i></a>InputFile</h4>
<p>This object represents the contents of a file to be uploaded. Must be posted using multipart/form-data in the usual way that files are uploaded via the browser.</p>
<h4><a class="anchor" name="sending-files" href="#sending-files"><i class="anchor-icon"></i></a>Sending files</h4>
<p> There are three ways to send files (photos, stickers, audio, media, etc.):</p>
<ol>
<li>If the file is already stored somewhere on the Telegram servers, you don&#39;t need to reupload it: each file object has a <strong>file_id</strong> field, simply pass this <strong>file_id</strong> as a parameter instead of uploading. There are <strong>no limits</strong> for files sent this way.</li>
<li>Provide Telegram with an HTTP URL for the file to be sent. Telegram will download and send the file. 5 MB max size for photos and 20 MB max for other types of content.</li>
<li>Post the file using multipart/form-data in the usual way that files are uploaded via the browser. 10 MB max size for photos, 50 MB for other files.</li>
</ol>
<p><strong>Sending by file_id</strong></p>
<ul>
<li>It is not possible to change the file type when resending by <strong>file_id</strong>. I.e. a <a href="#video">video</a> can&#39;t be <a href="#sendphoto">sent as a photo</a>, a <a href="#photosize">photo</a> can&#39;t be <a href="#senddocument">sent as a document</a>, etc.</li>
<li>It is not possible to resend thumbnails.</li>
<li>Resending a photo by <strong>file_id</strong> will send all of its <a href="#photosize">sizes</a>.</li>
<li><strong>file_id</strong> is unique for each individual bot and <strong>can&#39;t</strong> be transferred from one bot to another.</li>
<li><strong>file_id</strong> uniquely identifies a file, but a file can have different valid <strong>file_id</strong>s even for the same bot.</li>
</ul>
<p><strong>Sending by URL</strong></p>
<ul>
<li>When sending by URL the target file must have the correct MIME type (e.g., audio/mpeg for <a href="#sendaudio">sendAudio</a>, etc.).</li>
<li>In <a href="#senddocument">sendDocument</a>, sending by URL will currently only work for <strong>GIF</strong>, <strong>PDF</strong> and <strong>ZIP</strong> files.</li>
<li>To use <a href="#sendvoice">sendVoice</a>, the file must have the type audio/ogg and be no more than 1MB in size. 1-20MB voice notes will be sent as files.</li>
<li>Other configurations may work but we can&#39;t guarantee that they will.</li>
</ul>
<h4><a class="anchor" name="inline-mode-objects" href="#inline-mode-objects"><i class="anchor-icon"></i></a>Inline mode objects</h4>
<p>Objects and methods used in the inline mode are described in the <a href="#inline-mode">Inline mode section</a>.</p>
<h3><a class="anchor" name="available-methods" href="#available-methods"><i class="anchor-icon"></i></a>Available methods</h3>
<blockquote>
<p>All methods in the Bot API are case-insensitive. We support <strong>GET</strong> and <strong>POST</strong> HTTP methods. Use either <a href="https://en.wikipedia.org/wiki/Query_string">URL query string</a> or <em>application/json</em> or <em>application/x-www-form-urlencoded</em> or <em>multipart/form-data</em> for passing parameters in Bot API requests.<br>On successful call, a JSON-object containing the result will be returned.</p>
</blockquote>
<h4><a class="anchor" name="getme" href="#getme"><i class="anchor-icon"></i></a>getMe</h4>
<p>A simple method for testing your bot&#39;s authentication token. Requires no parameters. Returns basic information about the bot in form of a <a href="#user">User</a> object.</p>
<h4><a class="anchor" name="logout" href="#logout"><i class="anchor-icon"></i></a>logOut</h4>
<p>Use this method to log out from the cloud Bot API server before launching the bot locally. You <strong>must</strong> log out the bot before running it locally, otherwise there is no guarantee that the bot will receive updates. After a successful call, you can immediately log in on a local server, but will not be able to log in back to the cloud Bot API server for 10 minutes. Returns <em>True</em> on success. Requires no parameters.</p>
<h4><a class="anchor" name="close" href="#close"><i class="anchor-icon"></i></a>close</h4>
<p>Use this method to close the bot instance before moving it from one local server to another. You need to delete the webhook before calling this method to ensure that the bot isn&#39;t launched again after server restart. The method will return error 429 in the first 10 minutes after the bot is launched. Returns <em>True</em> on success. Requires no parameters.</p>
<h4><a class="anchor" name="sendmessage" href="#sendmessage"><i class="anchor-icon"></i></a>sendMessage</h4>
<p>Use this method to send text messages. On success, the sent <a href="#message">Message</a> is returned.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>text</td>
<td>String</td>
<td>Yes</td>
<td>Text of the message to be sent, 1-4096 characters after entities parsing</td>
</tr>
<tr>
<td>parse_mode</td>
<td>String</td>
<td>Optional</td>
<td>Mode for parsing entities in the message text. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td>Optional</td>
<td>A JSON-serialized list of special entities that appear in message text, which can be specified instead of <em>parse_mode</em></td>
</tr>
<tr>
<td>disable_web_page_preview</td>
<td>Boolean</td>
<td>Optional</td>
<td>Disables link previews for links in this message</td>
</tr>
<tr>
<td>disable_notification</td>
<td>Boolean</td>
<td>Optional</td>
<td>Sends the message <a href="https://telegram.org/blog/channels-2-0#silent-messages">silently</a>. Users will receive a notification with no sound.</td>
</tr>
<tr>
<td>protect_content</td>
<td>Boolean</td>
<td>Optional</td>
<td>Protects the contents of the sent message from forwarding and saving</td>
</tr>
<tr>
<td>reply_to_message_id</td>
<td>Integer</td>
<td>Optional</td>
<td>If the message is a reply, ID of the original message</td>
</tr>
<tr>
<td>allow_sending_without_reply</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the message should be sent even if the specified replied-to message is not found</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a> or <a href="#replykeyboardmarkup">ReplyKeyboardMarkup</a> or <a href="#replykeyboardremove">ReplyKeyboardRemove</a> or <a href="#forcereply">ForceReply</a></td>
<td>Optional</td>
<td>Additional interface options. A JSON-serialized object for an <a href="https://core.telegram.org/bots#inline-keyboards-and-on-the-fly-updating">inline keyboard</a>, <a href="https://core.telegram.org/bots#keyboards">custom reply keyboard</a>, instructions to remove reply keyboard or to force a reply from the user.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="formatting-options" href="#formatting-options"><i class="anchor-icon"></i></a>Formatting options</h4>
<p>The Bot API supports basic formatting for messages. You can use bold, italic, underlined, strikethrough, and spoiler text, as well as inline links and pre-formatted code in your bots&#39; messages. Telegram clients will render them accordingly. You can use either markdown-style or HTML-style formatting.</p>
<p>Note that Telegram clients will display an <strong>alert</strong> to the user before opening an inline link (&#39;Open this link?&#39; together with the full URL).</p>
<p>Message entities can be nested, providing following restrictions are met:<br>- If two entities have common characters then one of them is fully contained inside another.<br>- <em>bold</em>, <em>italic</em>, <em>underline</em>, <em>strikethrough</em>, and <em>spoiler</em> entities can contain and can be part of any other entities, except <em>pre</em> and <em>code</em>.<br>- All other entities can&#39;t contain each other.</p>
<p>Links <code>tg://user?id=&lt;user_id&gt;</code> can be used to mention a user by their ID without using a username. Please note:</p>
<ul>
<li>These links will work <strong>only</strong> if they are used inside an inline link or in an inline keyboard button. For example, they will not work, when used in a message text.</li>
<li>These mentions are only guaranteed to work if the user has contacted the bot in the past, has sent a callback query to the bot via an inline button or is a member in the group where he was mentioned.</li>
</ul>
<h6><a class="anchor" name="markdownv2-style" href="#markdownv2-style"><i class="anchor-icon"></i></a>MarkdownV2 style</h6>
<p>To use this mode, pass <em>MarkdownV2</em> in the <em>parse_mode</em> field. Use the following syntax in your message:</p>
<pre><code>*bold \*text*
_italic \*text_
__underline__
~strikethrough~
||spoiler||
*bold _italic bold ~italic bold strikethrough ||italic bold strikethrough spoiler||~ __underline italic bold___ bold*
[inline URL](http://www.example.com/)
[inline mention of a user](tg://user?id=123456789)
`inline fixed-width code`
```
pre-formatted fixed-width code block
```
```python
pre-formatted fixed-width code block written in the Python programming language
```</code></pre>
<p>Please note:</p>
<ul>
<li>Any character with code between 1 and 126 inclusively can be escaped anywhere with a preceding &#39;\&#39; character, in which case it is treated as an ordinary character and not a part of the markup. This implies that &#39;\&#39; character usually must be escaped with a preceding &#39;\&#39; character.</li>
<li>Inside <code>pre</code> and <code>code</code> entities, all &#39;`&#39; and &#39;\&#39; characters must be escaped with a preceding &#39;\&#39; character.</li>
<li>Inside <code>(...)</code> part of inline link definition, all &#39;)&#39; and &#39;\&#39; must be escaped with a preceding &#39;\&#39; character.</li>
<li>In all other places characters &#39;_&#39;, &#39;*&#39;, &#39;[&#39;, &#39;]&#39;, &#39;(&#39;, &#39;)&#39;, &#39;~&#39;, &#39;`&#39;, &#39;&gt;&#39;, &#39;#&#39;, &#39;+&#39;, &#39;-&#39;, &#39;=&#39;, &#39;|&#39;, &#39;{&#39;, &#39;}&#39;, &#39;.&#39;, &#39;!&#39; must be escaped with the preceding character &#39;\&#39;.</li>
<li>In case of ambiguity between <code>italic</code> and <code>underline</code> entities <code>__</code> is always greadily treated from left to right as beginning or end of <code>underline</code> entity, so instead of <code>___italic underline___</code> use <code>___italic underline_\r__</code>, where <code>\r</code> is a character with code 13, which will be ignored.</li>
</ul>
<h6><a class="anchor" name="html-style" href="#html-style"><i class="anchor-icon"></i></a>HTML style</h6>
<p>To use this mode, pass <em>HTML</em> in the <em>parse_mode</em> field. The following tags are currently supported:</p>
<pre><code>&lt;b&gt;bold&lt;/b&gt;, &lt;strong&gt;bold&lt;/strong&gt;
&lt;i&gt;italic&lt;/i&gt;, &lt;em&gt;italic&lt;/em&gt;
&lt;u&gt;underline&lt;/u&gt;, &lt;ins&gt;underline&lt;/ins&gt;
&lt;s&gt;strikethrough&lt;/s&gt;, &lt;strike&gt;strikethrough&lt;/strike&gt;, &lt;del&gt;strikethrough&lt;/del&gt;
&lt;span class=&quot;tg-spoiler&quot;&gt;spoiler&lt;/span&gt;, &lt;tg-spoiler&gt;spoiler&lt;/tg-spoiler&gt;
&lt;b&gt;bold &lt;i&gt;italic bold &lt;s&gt;italic bold strikethrough &lt;span class=&quot;tg-spoiler&quot;&gt;italic bold strikethrough spoiler&lt;/span&gt;&lt;/s&gt; &lt;u&gt;underline italic bold&lt;/u&gt;&lt;/i&gt; bold&lt;/b&gt;
&lt;a href=&quot;http://www.example.com/&quot;&gt;inline URL&lt;/a&gt;
&lt;a href=&quot;tg://user?id=123456789&quot;&gt;inline mention of a user&lt;/a&gt;
&lt;code&gt;inline fixed-width code&lt;/code&gt;
&lt;pre&gt;pre-formatted fixed-width code block&lt;/pre&gt;
&lt;pre&gt;&lt;code class=&quot;language-python&quot;&gt;pre-formatted fixed-width code block written in the Python programming language&lt;/code&gt;&lt;/pre&gt;</code></pre>
<p>Please note:</p>
<ul>
<li>Only the tags mentioned above are currently supported.</li>
<li>All <code>&lt;</code>, <code>&gt;</code> and <code>&amp;</code> symbols that are not a part of a tag or an HTML entity must be replaced with the corresponding HTML entities (<code>&lt;</code> with <code>&amp;lt;</code>, <code>&gt;</code> with <code>&amp;gt;</code> and <code>&amp;</code> with <code>&amp;amp;</code>).</li>
<li>All numerical HTML entities are supported.</li>
<li>The API currently supports only the following named HTML entities: <code>&amp;lt;</code>, <code>&amp;gt;</code>, <code>&amp;amp;</code> and <code>&amp;quot;</code>.</li>
<li>Use nested <code>pre</code> and <code>code</code> tags, to define programming language for <code>pre</code> entity.</li>
<li>Programming language can&#39;t be specified for standalone <code>code</code> tags.</li>
</ul>
<h6><a class="anchor" name="markdown-style" href="#markdown-style"><i class="anchor-icon"></i></a>Markdown style</h6>
<p>This is a legacy mode, retained for backward compatibility. To use this mode, pass <em>Markdown</em> in the <em>parse_mode</em> field. Use the following syntax in your message:</p>
<pre><code>*bold text*
_italic text_
[inline URL](http://www.example.com/)
[inline mention of a user](tg://user?id=123456789)
`inline fixed-width code`
```
pre-formatted fixed-width code block
```
```python
pre-formatted fixed-width code block written in the Python programming language
```</code></pre>
<p>Please note:</p>
<ul>
<li>Entities must not be nested, use parse mode <a href="#markdownv2-style">MarkdownV2</a> instead.</li>
<li>There is no way to specify underline and strikethrough entities, use parse mode <a href="#markdownv2-style">MarkdownV2</a> instead.</li>
<li>To escape characters &#39;_&#39;, &#39;*&#39;, &#39;`&#39;, &#39;[&#39; outside of an entity, prepend the characters &#39;\&#39; before them.</li>
<li>Escaping inside entities is not allowed, so entity must be closed first and reopened again: use <code>_snake_\__case_</code> for italic <code>snake_case</code> and <code>*2*\**2=4*</code> for bold <code>2*2=4</code>.</li>
</ul>
<h4><a class="anchor" name="forwardmessage" href="#forwardmessage"><i class="anchor-icon"></i></a>forwardMessage</h4>
<p>Use this method to forward messages of any kind. Service messages can&#39;t be forwarded. On success, the sent <a href="#message">Message</a> is returned.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>from_chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the chat where the original message was sent (or channel username in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>disable_notification</td>
<td>Boolean</td>
<td>Optional</td>
<td>Sends the message <a href="https://telegram.org/blog/channels-2-0#silent-messages">silently</a>. Users will receive a notification with no sound.</td>
</tr>
<tr>
<td>protect_content</td>
<td>Boolean</td>
<td>Optional</td>
<td>Protects the contents of the forwarded message from forwarding and saving</td>
</tr>
<tr>
<td>message_id</td>
<td>Integer</td>
<td>Yes</td>
<td>Message identifier in the chat specified in <em>from_chat_id</em></td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="copymessage" href="#copymessage"><i class="anchor-icon"></i></a>copyMessage</h4>
<p>Use this method to copy messages of any kind. Service messages and invoice messages can&#39;t be copied. The method is analogous to the method <a href="#forwardmessage">forwardMessage</a>, but the copied message doesn&#39;t have a link to the original message. Returns the <a href="#messageid">MessageId</a> of the sent message on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>from_chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the chat where the original message was sent (or channel username in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>message_id</td>
<td>Integer</td>
<td>Yes</td>
<td>Message identifier in the chat specified in <em>from_chat_id</em></td>
</tr>
<tr>
<td>caption</td>
<td>String</td>
<td>Optional</td>
<td>New caption for media, 0-1024 characters after entities parsing. If not specified, the original caption is kept</td>
</tr>
<tr>
<td>parse_mode</td>
<td>String</td>
<td>Optional</td>
<td>Mode for parsing entities in the new caption. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>caption_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td>Optional</td>
<td>A JSON-serialized list of special entities that appear in the new caption, which can be specified instead of <em>parse_mode</em></td>
</tr>
<tr>
<td>disable_notification</td>
<td>Boolean</td>
<td>Optional</td>
<td>Sends the message <a href="https://telegram.org/blog/channels-2-0#silent-messages">silently</a>. Users will receive a notification with no sound.</td>
</tr>
<tr>
<td>protect_content</td>
<td>Boolean</td>
<td>Optional</td>
<td>Protects the contents of the sent message from forwarding and saving</td>
</tr>
<tr>
<td>reply_to_message_id</td>
<td>Integer</td>
<td>Optional</td>
<td>If the message is a reply, ID of the original message</td>
</tr>
<tr>
<td>allow_sending_without_reply</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the message should be sent even if the specified replied-to message is not found</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a> or <a href="#replykeyboardmarkup">ReplyKeyboardMarkup</a> or <a href="#replykeyboardremove">ReplyKeyboardRemove</a> or <a href="#forcereply">ForceReply</a></td>
<td>Optional</td>
<td>Additional interface options. A JSON-serialized object for an <a href="https://core.telegram.org/bots#inline-keyboards-and-on-the-fly-updating">inline keyboard</a>, <a href="https://core.telegram.org/bots#keyboards">custom reply keyboard</a>, instructions to remove reply keyboard or to force a reply from the user.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="sendphoto" href="#sendphoto"><i class="anchor-icon"></i></a>sendPhoto</h4>
<p>Use this method to send photos. On success, the sent <a href="#message">Message</a> is returned.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>photo</td>
<td><a href="#inputfile">InputFile</a> or String</td>
<td>Yes</td>
<td>Photo to send. Pass a file_id as String to send a photo that exists on the Telegram servers (recommended), pass an HTTP URL as a String for Telegram to get a photo from the Internet, or upload a new photo using multipart/form-data. The photo must be at most 10 MB in size. The photo&#39;s width and height must not exceed 10000 in total. Width and height ratio must be at most 20. <a href="#sending-files">More info on Sending Files »</a></td>
</tr>
<tr>
<td>caption</td>
<td>String</td>
<td>Optional</td>
<td>Photo caption (may also be used when resending photos by <em>file_id</em>), 0-1024 characters after entities parsing</td>
</tr>
<tr>
<td>parse_mode</td>
<td>String</td>
<td>Optional</td>
<td>Mode for parsing entities in the photo caption. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>caption_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td>Optional</td>
<td>A JSON-serialized list of special entities that appear in the caption, which can be specified instead of <em>parse_mode</em></td>
</tr>
<tr>
<td>disable_notification</td>
<td>Boolean</td>
<td>Optional</td>
<td>Sends the message <a href="https://telegram.org/blog/channels-2-0#silent-messages">silently</a>. Users will receive a notification with no sound.</td>
</tr>
<tr>
<td>protect_content</td>
<td>Boolean</td>
<td>Optional</td>
<td>Protects the contents of the sent message from forwarding and saving</td>
</tr>
<tr>
<td>reply_to_message_id</td>
<td>Integer</td>
<td>Optional</td>
<td>If the message is a reply, ID of the original message</td>
</tr>
<tr>
<td>allow_sending_without_reply</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the message should be sent even if the specified replied-to message is not found</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a> or <a href="#replykeyboardmarkup">ReplyKeyboardMarkup</a> or <a href="#replykeyboardremove">ReplyKeyboardRemove</a> or <a href="#forcereply">ForceReply</a></td>
<td>Optional</td>
<td>Additional interface options. A JSON-serialized object for an <a href="https://core.telegram.org/bots#inline-keyboards-and-on-the-fly-updating">inline keyboard</a>, <a href="https://core.telegram.org/bots#keyboards">custom reply keyboard</a>, instructions to remove reply keyboard or to force a reply from the user.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="sendaudio" href="#sendaudio"><i class="anchor-icon"></i></a>sendAudio</h4>
<p>Use this method to send audio files, if you want Telegram clients to display them in the music player. Your audio must be in the .MP3 or .M4A format. On success, the sent <a href="#message">Message</a> is returned. Bots can currently send audio files of up to 50 MB in size, this limit may be changed in the future.</p>
<p>For sending voice messages, use the <a href="#sendvoice">sendVoice</a> method instead.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>audio</td>
<td><a href="#inputfile">InputFile</a> or String</td>
<td>Yes</td>
<td>Audio file to send. Pass a file_id as String to send an audio file that exists on the Telegram servers (recommended), pass an HTTP URL as a String for Telegram to get an audio file from the Internet, or upload a new one using multipart/form-data. <a href="#sending-files">More info on Sending Files »</a></td>
</tr>
<tr>
<td>caption</td>
<td>String</td>
<td>Optional</td>
<td>Audio caption, 0-1024 characters after entities parsing</td>
</tr>
<tr>
<td>parse_mode</td>
<td>String</td>
<td>Optional</td>
<td>Mode for parsing entities in the audio caption. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>caption_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td>Optional</td>
<td>A JSON-serialized list of special entities that appear in the caption, which can be specified instead of <em>parse_mode</em></td>
</tr>
<tr>
<td>duration</td>
<td>Integer</td>
<td>Optional</td>
<td>Duration of the audio in seconds</td>
</tr>
<tr>
<td>performer</td>
<td>String</td>
<td>Optional</td>
<td>Performer</td>
</tr>
<tr>
<td>title</td>
<td>String</td>
<td>Optional</td>
<td>Track name</td>
</tr>
<tr>
<td>thumb</td>
<td><a href="#inputfile">InputFile</a> or String</td>
<td>Optional</td>
<td>Thumbnail of the file sent; can be ignored if thumbnail generation for the file is supported server-side. The thumbnail should be in JPEG format and less than 200 kB in size. A thumbnail&#39;s width and height should not exceed 320. Ignored if the file is not uploaded using multipart/form-data. Thumbnails can&#39;t be reused and can be only uploaded as a new file, so you can pass “attach://&lt;file_attach_name&gt;” if the thumbnail was uploaded using multipart/form-data under &lt;file_attach_name&gt;. <a href="#sending-files">More info on Sending Files »</a></td>
</tr>
<tr>
<td>disable_notification</td>
<td>Boolean</td>
<td>Optional</td>
<td>Sends the message <a href="https://telegram.org/blog/channels-2-0#silent-messages">silently</a>. Users will receive a notification with no sound.</td>
</tr>
<tr>
<td>protect_content</td>
<td>Boolean</td>
<td>Optional</td>
<td>Protects the contents of the sent message from forwarding and saving</td>
</tr>
<tr>
<td>reply_to_message_id</td>
<td>Integer</td>
<td>Optional</td>
<td>If the message is a reply, ID of the original message</td>
</tr>
<tr>
<td>allow_sending_without_reply</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the message should be sent even if the specified replied-to message is not found</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a> or <a href="#replykeyboardmarkup">ReplyKeyboardMarkup</a> or <a href="#replykeyboardremove">ReplyKeyboardRemove</a> or <a href="#forcereply">ForceReply</a></td>
<td>Optional</td>
<td>Additional interface options. A JSON-serialized object for an <a href="https://core.telegram.org/bots#inline-keyboards-and-on-the-fly-updating">inline keyboard</a>, <a href="https://core.telegram.org/bots#keyboards">custom reply keyboard</a>, instructions to remove reply keyboard or to force a reply from the user.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="senddocument" href="#senddocument"><i class="anchor-icon"></i></a>sendDocument</h4>
<p>Use this method to send general files. On success, the sent <a href="#message">Message</a> is returned. Bots can currently send files of any type of up to 50 MB in size, this limit may be changed in the future.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>document</td>
<td><a href="#inputfile">InputFile</a> or String</td>
<td>Yes</td>
<td>File to send. Pass a file_id as String to send a file that exists on the Telegram servers (recommended), pass an HTTP URL as a String for Telegram to get a file from the Internet, or upload a new one using multipart/form-data. <a href="#sending-files">More info on Sending Files »</a></td>
</tr>
<tr>
<td>thumb</td>
<td><a href="#inputfile">InputFile</a> or String</td>
<td>Optional</td>
<td>Thumbnail of the file sent; can be ignored if thumbnail generation for the file is supported server-side. The thumbnail should be in JPEG format and less than 200 kB in size. A thumbnail&#39;s width and height should not exceed 320. Ignored if the file is not uploaded using multipart/form-data. Thumbnails can&#39;t be reused and can be only uploaded as a new file, so you can pass “attach://&lt;file_attach_name&gt;” if the thumbnail was uploaded using multipart/form-data under &lt;file_attach_name&gt;. <a href="#sending-files">More info on Sending Files »</a></td>
</tr>
<tr>
<td>caption</td>
<td>String</td>
<td>Optional</td>
<td>Document caption (may also be used when resending documents by <em>file_id</em>), 0-1024 characters after entities parsing</td>
</tr>
<tr>
<td>parse_mode</td>
<td>String</td>
<td>Optional</td>
<td>Mode for parsing entities in the document caption. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>caption_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td>Optional</td>
<td>A JSON-serialized list of special entities that appear in the caption, which can be specified instead of <em>parse_mode</em></td>
</tr>
<tr>
<td>disable_content_type_detection</td>
<td>Boolean</td>
<td>Optional</td>
<td>Disables automatic server-side content type detection for files uploaded using multipart/form-data</td>
</tr>
<tr>
<td>disable_notification</td>
<td>Boolean</td>
<td>Optional</td>
<td>Sends the message <a href="https://telegram.org/blog/channels-2-0#silent-messages">silently</a>. Users will receive a notification with no sound.</td>
</tr>
<tr>
<td>protect_content</td>
<td>Boolean</td>
<td>Optional</td>
<td>Protects the contents of the sent message from forwarding and saving</td>
</tr>
<tr>
<td>reply_to_message_id</td>
<td>Integer</td>
<td>Optional</td>
<td>If the message is a reply, ID of the original message</td>
</tr>
<tr>
<td>allow_sending_without_reply</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the message should be sent even if the specified replied-to message is not found</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a> or <a href="#replykeyboardmarkup">ReplyKeyboardMarkup</a> or <a href="#replykeyboardremove">ReplyKeyboardRemove</a> or <a href="#forcereply">ForceReply</a></td>
<td>Optional</td>
<td>Additional interface options. A JSON-serialized object for an <a href="https://core.telegram.org/bots#inline-keyboards-and-on-the-fly-updating">inline keyboard</a>, <a href="https://core.telegram.org/bots#keyboards">custom reply keyboard</a>, instructions to remove reply keyboard or to force a reply from the user.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="sendvideo" href="#sendvideo"><i class="anchor-icon"></i></a>sendVideo</h4>
<p>Use this method to send video files, Telegram clients support mp4 videos (other formats may be sent as <a href="#document">Document</a>). On success, the sent <a href="#message">Message</a> is returned. Bots can currently send video files of up to 50 MB in size, this limit may be changed in the future.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>video</td>
<td><a href="#inputfile">InputFile</a> or String</td>
<td>Yes</td>
<td>Video to send. Pass a file_id as String to send a video that exists on the Telegram servers (recommended), pass an HTTP URL as a String for Telegram to get a video from the Internet, or upload a new video using multipart/form-data. <a href="#sending-files">More info on Sending Files »</a></td>
</tr>
<tr>
<td>duration</td>
<td>Integer</td>
<td>Optional</td>
<td>Duration of sent video in seconds</td>
</tr>
<tr>
<td>width</td>
<td>Integer</td>
<td>Optional</td>
<td>Video width</td>
</tr>
<tr>
<td>height</td>
<td>Integer</td>
<td>Optional</td>
<td>Video height</td>
</tr>
<tr>
<td>thumb</td>
<td><a href="#inputfile">InputFile</a> or String</td>
<td>Optional</td>
<td>Thumbnail of the file sent; can be ignored if thumbnail generation for the file is supported server-side. The thumbnail should be in JPEG format and less than 200 kB in size. A thumbnail&#39;s width and height should not exceed 320. Ignored if the file is not uploaded using multipart/form-data. Thumbnails can&#39;t be reused and can be only uploaded as a new file, so you can pass “attach://&lt;file_attach_name&gt;” if the thumbnail was uploaded using multipart/form-data under &lt;file_attach_name&gt;. <a href="#sending-files">More info on Sending Files »</a></td>
</tr>
<tr>
<td>caption</td>
<td>String</td>
<td>Optional</td>
<td>Video caption (may also be used when resending videos by <em>file_id</em>), 0-1024 characters after entities parsing</td>
</tr>
<tr>
<td>parse_mode</td>
<td>String</td>
<td>Optional</td>
<td>Mode for parsing entities in the video caption. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>caption_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td>Optional</td>
<td>A JSON-serialized list of special entities that appear in the caption, which can be specified instead of <em>parse_mode</em></td>
</tr>
<tr>
<td>supports_streaming</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the uploaded video is suitable for streaming</td>
</tr>
<tr>
<td>disable_notification</td>
<td>Boolean</td>
<td>Optional</td>
<td>Sends the message <a href="https://telegram.org/blog/channels-2-0#silent-messages">silently</a>. Users will receive a notification with no sound.</td>
</tr>
<tr>
<td>protect_content</td>
<td>Boolean</td>
<td>Optional</td>
<td>Protects the contents of the sent message from forwarding and saving</td>
</tr>
<tr>
<td>reply_to_message_id</td>
<td>Integer</td>
<td>Optional</td>
<td>If the message is a reply, ID of the original message</td>
</tr>
<tr>
<td>allow_sending_without_reply</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the message should be sent even if the specified replied-to message is not found</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a> or <a href="#replykeyboardmarkup">ReplyKeyboardMarkup</a> or <a href="#replykeyboardremove">ReplyKeyboardRemove</a> or <a href="#forcereply">ForceReply</a></td>
<td>Optional</td>
<td>Additional interface options. A JSON-serialized object for an <a href="https://core.telegram.org/bots#inline-keyboards-and-on-the-fly-updating">inline keyboard</a>, <a href="https://core.telegram.org/bots#keyboards">custom reply keyboard</a>, instructions to remove reply keyboard or to force a reply from the user.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="sendanimation" href="#sendanimation"><i class="anchor-icon"></i></a>sendAnimation</h4>
<p>Use this method to send animation files (GIF or H.264/MPEG-4 AVC video without sound). On success, the sent <a href="#message">Message</a> is returned. Bots can currently send animation files of up to 50 MB in size, this limit may be changed in the future.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>animation</td>
<td><a href="#inputfile">InputFile</a> or String</td>
<td>Yes</td>
<td>Animation to send. Pass a file_id as String to send an animation that exists on the Telegram servers (recommended), pass an HTTP URL as a String for Telegram to get an animation from the Internet, or upload a new animation using multipart/form-data. <a href="#sending-files">More info on Sending Files »</a></td>
</tr>
<tr>
<td>duration</td>
<td>Integer</td>
<td>Optional</td>
<td>Duration of sent animation in seconds</td>
</tr>
<tr>
<td>width</td>
<td>Integer</td>
<td>Optional</td>
<td>Animation width</td>
</tr>
<tr>
<td>height</td>
<td>Integer</td>
<td>Optional</td>
<td>Animation height</td>
</tr>
<tr>
<td>thumb</td>
<td><a href="#inputfile">InputFile</a> or String</td>
<td>Optional</td>
<td>Thumbnail of the file sent; can be ignored if thumbnail generation for the file is supported server-side. The thumbnail should be in JPEG format and less than 200 kB in size. A thumbnail&#39;s width and height should not exceed 320. Ignored if the file is not uploaded using multipart/form-data. Thumbnails can&#39;t be reused and can be only uploaded as a new file, so you can pass “attach://&lt;file_attach_name&gt;” if the thumbnail was uploaded using multipart/form-data under &lt;file_attach_name&gt;. <a href="#sending-files">More info on Sending Files »</a></td>
</tr>
<tr>
<td>caption</td>
<td>String</td>
<td>Optional</td>
<td>Animation caption (may also be used when resending animation by <em>file_id</em>), 0-1024 characters after entities parsing</td>
</tr>
<tr>
<td>parse_mode</td>
<td>String</td>
<td>Optional</td>
<td>Mode for parsing entities in the animation caption. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>caption_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td>Optional</td>
<td>A JSON-serialized list of special entities that appear in the caption, which can be specified instead of <em>parse_mode</em></td>
</tr>
<tr>
<td>disable_notification</td>
<td>Boolean</td>
<td>Optional</td>
<td>Sends the message <a href="https://telegram.org/blog/channels-2-0#silent-messages">silently</a>. Users will receive a notification with no sound.</td>
</tr>
<tr>
<td>protect_content</td>
<td>Boolean</td>
<td>Optional</td>
<td>Protects the contents of the sent message from forwarding and saving</td>
</tr>
<tr>
<td>reply_to_message_id</td>
<td>Integer</td>
<td>Optional</td>
<td>If the message is a reply, ID of the original message</td>
</tr>
<tr>
<td>allow_sending_without_reply</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the message should be sent even if the specified replied-to message is not found</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a> or <a href="#replykeyboardmarkup">ReplyKeyboardMarkup</a> or <a href="#replykeyboardremove">ReplyKeyboardRemove</a> or <a href="#forcereply">ForceReply</a></td>
<td>Optional</td>
<td>Additional interface options. A JSON-serialized object for an <a href="https://core.telegram.org/bots#inline-keyboards-and-on-the-fly-updating">inline keyboard</a>, <a href="https://core.telegram.org/bots#keyboards">custom reply keyboard</a>, instructions to remove reply keyboard or to force a reply from the user.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="sendvoice" href="#sendvoice"><i class="anchor-icon"></i></a>sendVoice</h4>
<p>Use this method to send audio files, if you want Telegram clients to display the file as a playable voice message. For this to work, your audio must be in an .OGG file encoded with OPUS (other formats may be sent as <a href="#audio">Audio</a> or <a href="#document">Document</a>). On success, the sent <a href="#message">Message</a> is returned. Bots can currently send voice messages of up to 50 MB in size, this limit may be changed in the future.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>voice</td>
<td><a href="#inputfile">InputFile</a> or String</td>
<td>Yes</td>
<td>Audio file to send. Pass a file_id as String to send a file that exists on the Telegram servers (recommended), pass an HTTP URL as a String for Telegram to get a file from the Internet, or upload a new one using multipart/form-data. <a href="#sending-files">More info on Sending Files »</a></td>
</tr>
<tr>
<td>caption</td>
<td>String</td>
<td>Optional</td>
<td>Voice message caption, 0-1024 characters after entities parsing</td>
</tr>
<tr>
<td>parse_mode</td>
<td>String</td>
<td>Optional</td>
<td>Mode for parsing entities in the voice message caption. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>caption_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td>Optional</td>
<td>A JSON-serialized list of special entities that appear in the caption, which can be specified instead of <em>parse_mode</em></td>
</tr>
<tr>
<td>duration</td>
<td>Integer</td>
<td>Optional</td>
<td>Duration of the voice message in seconds</td>
</tr>
<tr>
<td>disable_notification</td>
<td>Boolean</td>
<td>Optional</td>
<td>Sends the message <a href="https://telegram.org/blog/channels-2-0#silent-messages">silently</a>. Users will receive a notification with no sound.</td>
</tr>
<tr>
<td>protect_content</td>
<td>Boolean</td>
<td>Optional</td>
<td>Protects the contents of the sent message from forwarding and saving</td>
</tr>
<tr>
<td>reply_to_message_id</td>
<td>Integer</td>
<td>Optional</td>
<td>If the message is a reply, ID of the original message</td>
</tr>
<tr>
<td>allow_sending_without_reply</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the message should be sent even if the specified replied-to message is not found</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a> or <a href="#replykeyboardmarkup">ReplyKeyboardMarkup</a> or <a href="#replykeyboardremove">ReplyKeyboardRemove</a> or <a href="#forcereply">ForceReply</a></td>
<td>Optional</td>
<td>Additional interface options. A JSON-serialized object for an <a href="https://core.telegram.org/bots#inline-keyboards-and-on-the-fly-updating">inline keyboard</a>, <a href="https://core.telegram.org/bots#keyboards">custom reply keyboard</a>, instructions to remove reply keyboard or to force a reply from the user.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="sendvideonote" href="#sendvideonote"><i class="anchor-icon"></i></a>sendVideoNote</h4>
<p>As of <a href="https://telegram.org/blog/video-messages-and-telescope">v.4.0</a>, Telegram clients support rounded square mp4 videos of up to 1 minute long. Use this method to send video messages. On success, the sent <a href="#message">Message</a> is returned.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>video_note</td>
<td><a href="#inputfile">InputFile</a> or String</td>
<td>Yes</td>
<td>Video note to send. Pass a file_id as String to send a video note that exists on the Telegram servers (recommended) or upload a new video using multipart/form-data. <a href="#sending-files">More info on Sending Files »</a>. Sending video notes by a URL is currently unsupported</td>
</tr>
<tr>
<td>duration</td>
<td>Integer</td>
<td>Optional</td>
<td>Duration of sent video in seconds</td>
</tr>
<tr>
<td>length</td>
<td>Integer</td>
<td>Optional</td>
<td>Video width and height, i.e. diameter of the video message</td>
</tr>
<tr>
<td>thumb</td>
<td><a href="#inputfile">InputFile</a> or String</td>
<td>Optional</td>
<td>Thumbnail of the file sent; can be ignored if thumbnail generation for the file is supported server-side. The thumbnail should be in JPEG format and less than 200 kB in size. A thumbnail&#39;s width and height should not exceed 320. Ignored if the file is not uploaded using multipart/form-data. Thumbnails can&#39;t be reused and can be only uploaded as a new file, so you can pass “attach://&lt;file_attach_name&gt;” if the thumbnail was uploaded using multipart/form-data under &lt;file_attach_name&gt;. <a href="#sending-files">More info on Sending Files »</a></td>
</tr>
<tr>
<td>disable_notification</td>
<td>Boolean</td>
<td>Optional</td>
<td>Sends the message <a href="https://telegram.org/blog/channels-2-0#silent-messages">silently</a>. Users will receive a notification with no sound.</td>
</tr>
<tr>
<td>protect_content</td>
<td>Boolean</td>
<td>Optional</td>
<td>Protects the contents of the sent message from forwarding and saving</td>
</tr>
<tr>
<td>reply_to_message_id</td>
<td>Integer</td>
<td>Optional</td>
<td>If the message is a reply, ID of the original message</td>
</tr>
<tr>
<td>allow_sending_without_reply</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the message should be sent even if the specified replied-to message is not found</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a> or <a href="#replykeyboardmarkup">ReplyKeyboardMarkup</a> or <a href="#replykeyboardremove">ReplyKeyboardRemove</a> or <a href="#forcereply">ForceReply</a></td>
<td>Optional</td>
<td>Additional interface options. A JSON-serialized object for an <a href="https://core.telegram.org/bots#inline-keyboards-and-on-the-fly-updating">inline keyboard</a>, <a href="https://core.telegram.org/bots#keyboards">custom reply keyboard</a>, instructions to remove reply keyboard or to force a reply from the user.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="sendmediagroup" href="#sendmediagroup"><i class="anchor-icon"></i></a>sendMediaGroup</h4>
<p>Use this method to send a group of photos, videos, documents or audios as an album. Documents and audio files can be only grouped in an album with messages of the same type. On success, an array of <a href="#message">Messages</a> that were sent is returned.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>media</td>
<td>Array of <a href="#inputmediaaudio">InputMediaAudio</a>, <a href="#inputmediadocument">InputMediaDocument</a>, <a href="#inputmediaphoto">InputMediaPhoto</a> and <a href="#inputmediavideo">InputMediaVideo</a></td>
<td>Yes</td>
<td>A JSON-serialized array describing messages to be sent, must include 2-10 items</td>
</tr>
<tr>
<td>disable_notification</td>
<td>Boolean</td>
<td>Optional</td>
<td>Sends messages <a href="https://telegram.org/blog/channels-2-0#silent-messages">silently</a>. Users will receive a notification with no sound.</td>
</tr>
<tr>
<td>protect_content</td>
<td>Boolean</td>
<td>Optional</td>
<td>Protects the contents of the sent messages from forwarding and saving</td>
</tr>
<tr>
<td>reply_to_message_id</td>
<td>Integer</td>
<td>Optional</td>
<td>If the messages are a reply, ID of the original message</td>
</tr>
<tr>
<td>allow_sending_without_reply</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the message should be sent even if the specified replied-to message is not found</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="sendlocation" href="#sendlocation"><i class="anchor-icon"></i></a>sendLocation</h4>
<p>Use this method to send point on the map. On success, the sent <a href="#message">Message</a> is returned.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>latitude</td>
<td>Float number</td>
<td>Yes</td>
<td>Latitude of the location</td>
</tr>
<tr>
<td>longitude</td>
<td>Float number</td>
<td>Yes</td>
<td>Longitude of the location</td>
</tr>
<tr>
<td>horizontal_accuracy</td>
<td>Float number</td>
<td>Optional</td>
<td>The radius of uncertainty for the location, measured in meters; 0-1500</td>
</tr>
<tr>
<td>live_period</td>
<td>Integer</td>
<td>Optional</td>
<td>Period in seconds for which the location will be updated (see <a href="https://telegram.org/blog/live-locations">Live Locations</a>, should be between 60 and 86400.</td>
</tr>
<tr>
<td>heading</td>
<td>Integer</td>
<td>Optional</td>
<td>For live locations, a direction in which the user is moving, in degrees. Must be between 1 and 360 if specified.</td>
</tr>
<tr>
<td>proximity_alert_radius</td>
<td>Integer</td>
<td>Optional</td>
<td>For live locations, a maximum distance for proximity alerts about approaching another chat member, in meters. Must be between 1 and 100000 if specified.</td>
</tr>
<tr>
<td>disable_notification</td>
<td>Boolean</td>
<td>Optional</td>
<td>Sends the message <a href="https://telegram.org/blog/channels-2-0#silent-messages">silently</a>. Users will receive a notification with no sound.</td>
</tr>
<tr>
<td>protect_content</td>
<td>Boolean</td>
<td>Optional</td>
<td>Protects the contents of the sent message from forwarding and saving</td>
</tr>
<tr>
<td>reply_to_message_id</td>
<td>Integer</td>
<td>Optional</td>
<td>If the message is a reply, ID of the original message</td>
</tr>
<tr>
<td>allow_sending_without_reply</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the message should be sent even if the specified replied-to message is not found</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a> or <a href="#replykeyboardmarkup">ReplyKeyboardMarkup</a> or <a href="#replykeyboardremove">ReplyKeyboardRemove</a> or <a href="#forcereply">ForceReply</a></td>
<td>Optional</td>
<td>Additional interface options. A JSON-serialized object for an <a href="https://core.telegram.org/bots#inline-keyboards-and-on-the-fly-updating">inline keyboard</a>, <a href="https://core.telegram.org/bots#keyboards">custom reply keyboard</a>, instructions to remove reply keyboard or to force a reply from the user.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="editmessagelivelocation" href="#editmessagelivelocation"><i class="anchor-icon"></i></a>editMessageLiveLocation</h4>
<p>Use this method to edit live location messages. A location can be edited until its <em>live_period</em> expires or editing is explicitly disabled by a call to <a href="#stopmessagelivelocation">stopMessageLiveLocation</a>. On success, if the edited message is not an inline message, the edited <a href="#message">Message</a> is returned, otherwise <em>True</em> is returned.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Optional</td>
<td>Required if <em>inline_message_id</em> is not specified. Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>message_id</td>
<td>Integer</td>
<td>Optional</td>
<td>Required if <em>inline_message_id</em> is not specified. Identifier of the message to edit</td>
</tr>
<tr>
<td>inline_message_id</td>
<td>String</td>
<td>Optional</td>
<td>Required if <em>chat_id</em> and <em>message_id</em> are not specified. Identifier of the inline message</td>
</tr>
<tr>
<td>latitude</td>
<td>Float number</td>
<td>Yes</td>
<td>Latitude of new location</td>
</tr>
<tr>
<td>longitude</td>
<td>Float number</td>
<td>Yes</td>
<td>Longitude of new location</td>
</tr>
<tr>
<td>horizontal_accuracy</td>
<td>Float number</td>
<td>Optional</td>
<td>The radius of uncertainty for the location, measured in meters; 0-1500</td>
</tr>
<tr>
<td>heading</td>
<td>Integer</td>
<td>Optional</td>
<td>Direction in which the user is moving, in degrees. Must be between 1 and 360 if specified.</td>
</tr>
<tr>
<td>proximity_alert_radius</td>
<td>Integer</td>
<td>Optional</td>
<td>Maximum distance for proximity alerts about approaching another chat member, in meters. Must be between 1 and 100000 if specified.</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a></td>
<td>Optional</td>
<td>A JSON-serialized object for a new <a href="https://core.telegram.org/bots#inline-keyboards-and-on-the-fly-updating">inline keyboard</a>.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="stopmessagelivelocation" href="#stopmessagelivelocation"><i class="anchor-icon"></i></a>stopMessageLiveLocation</h4>
<p>Use this method to stop updating a live location message before <em>live_period</em> expires. On success, if the message is not an inline message, the edited <a href="#message">Message</a> is returned, otherwise <em>True</em> is returned.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Optional</td>
<td>Required if <em>inline_message_id</em> is not specified. Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>message_id</td>
<td>Integer</td>
<td>Optional</td>
<td>Required if <em>inline_message_id</em> is not specified. Identifier of the message with live location to stop</td>
</tr>
<tr>
<td>inline_message_id</td>
<td>String</td>
<td>Optional</td>
<td>Required if <em>chat_id</em> and <em>message_id</em> are not specified. Identifier of the inline message</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a></td>
<td>Optional</td>
<td>A JSON-serialized object for a new <a href="https://core.telegram.org/bots#inline-keyboards-and-on-the-fly-updating">inline keyboard</a>.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="sendvenue" href="#sendvenue"><i class="anchor-icon"></i></a>sendVenue</h4>
<p>Use this method to send information about a venue. On success, the sent <a href="#message">Message</a> is returned.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>latitude</td>
<td>Float number</td>
<td>Yes</td>
<td>Latitude of the venue</td>
</tr>
<tr>
<td>longitude</td>
<td>Float number</td>
<td>Yes</td>
<td>Longitude of the venue</td>
</tr>
<tr>
<td>title</td>
<td>String</td>
<td>Yes</td>
<td>Name of the venue</td>
</tr>
<tr>
<td>address</td>
<td>String</td>
<td>Yes</td>
<td>Address of the venue</td>
</tr>
<tr>
<td>foursquare_id</td>
<td>String</td>
<td>Optional</td>
<td>Foursquare identifier of the venue</td>
</tr>
<tr>
<td>foursquare_type</td>
<td>String</td>
<td>Optional</td>
<td>Foursquare type of the venue, if known. (For example, “arts_entertainment/default”, “arts_entertainment/aquarium” or “food/icecream”.)</td>
</tr>
<tr>
<td>google_place_id</td>
<td>String</td>
<td>Optional</td>
<td>Google Places identifier of the venue</td>
</tr>
<tr>
<td>google_place_type</td>
<td>String</td>
<td>Optional</td>
<td>Google Places type of the venue. (See <a href="https://developers.google.com/places/web-service/supported_types">supported types</a>.)</td>
</tr>
<tr>
<td>disable_notification</td>
<td>Boolean</td>
<td>Optional</td>
<td>Sends the message <a href="https://telegram.org/blog/channels-2-0#silent-messages">silently</a>. Users will receive a notification with no sound.</td>
</tr>
<tr>
<td>protect_content</td>
<td>Boolean</td>
<td>Optional</td>
<td>Protects the contents of the sent message from forwarding and saving</td>
</tr>
<tr>
<td>reply_to_message_id</td>
<td>Integer</td>
<td>Optional</td>
<td>If the message is a reply, ID of the original message</td>
</tr>
<tr>
<td>allow_sending_without_reply</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the message should be sent even if the specified replied-to message is not found</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a> or <a href="#replykeyboardmarkup">ReplyKeyboardMarkup</a> or <a href="#replykeyboardremove">ReplyKeyboardRemove</a> or <a href="#forcereply">ForceReply</a></td>
<td>Optional</td>
<td>Additional interface options. A JSON-serialized object for an <a href="https://core.telegram.org/bots#inline-keyboards-and-on-the-fly-updating">inline keyboard</a>, <a href="https://core.telegram.org/bots#keyboards">custom reply keyboard</a>, instructions to remove reply keyboard or to force a reply from the user.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="sendcontact" href="#sendcontact"><i class="anchor-icon"></i></a>sendContact</h4>
<p>Use this method to send phone contacts. On success, the sent <a href="#message">Message</a> is returned.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>phone_number</td>
<td>String</td>
<td>Yes</td>
<td>Contact&#39;s phone number</td>
</tr>
<tr>
<td>first_name</td>
<td>String</td>
<td>Yes</td>
<td>Contact&#39;s first name</td>
</tr>
<tr>
<td>last_name</td>
<td>String</td>
<td>Optional</td>
<td>Contact&#39;s last name</td>
</tr>
<tr>
<td>vcard</td>
<td>String</td>
<td>Optional</td>
<td>Additional data about the contact in the form of a <a href="https://en.wikipedia.org/wiki/VCard">vCard</a>, 0-2048 bytes</td>
</tr>
<tr>
<td>disable_notification</td>
<td>Boolean</td>
<td>Optional</td>
<td>Sends the message <a href="https://telegram.org/blog/channels-2-0#silent-messages">silently</a>. Users will receive a notification with no sound.</td>
</tr>
<tr>
<td>protect_content</td>
<td>Boolean</td>
<td>Optional</td>
<td>Protects the contents of the sent message from forwarding and saving</td>
</tr>
<tr>
<td>reply_to_message_id</td>
<td>Integer</td>
<td>Optional</td>
<td>If the message is a reply, ID of the original message</td>
</tr>
<tr>
<td>allow_sending_without_reply</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the message should be sent even if the specified replied-to message is not found</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a> or <a href="#replykeyboardmarkup">ReplyKeyboardMarkup</a> or <a href="#replykeyboardremove">ReplyKeyboardRemove</a> or <a href="#forcereply">ForceReply</a></td>
<td>Optional</td>
<td>Additional interface options. A JSON-serialized object for an <a href="https://core.telegram.org/bots#inline-keyboards-and-on-the-fly-updating">inline keyboard</a>, <a href="https://core.telegram.org/bots#keyboards">custom reply keyboard</a>, instructions to remove keyboard or to force a reply from the user.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="sendpoll" href="#sendpoll"><i class="anchor-icon"></i></a>sendPoll</h4>
<p>Use this method to send a native poll. On success, the sent <a href="#message">Message</a> is returned.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>question</td>
<td>String</td>
<td>Yes</td>
<td>Poll question, 1-300 characters</td>
</tr>
<tr>
<td>options</td>
<td>Array of String</td>
<td>Yes</td>
<td>A JSON-serialized list of answer options, 2-10 strings 1-100 characters each</td>
</tr>
<tr>
<td>is_anonymous</td>
<td>Boolean</td>
<td>Optional</td>
<td><em>True</em>, if the poll needs to be anonymous, defaults to <em>True</em></td>
</tr>
<tr>
<td>type</td>
<td>String</td>
<td>Optional</td>
<td>Poll type, “quiz” or “regular”, defaults to “regular”</td>
</tr>
<tr>
<td>allows_multiple_answers</td>
<td>Boolean</td>
<td>Optional</td>
<td><em>True</em>, if the poll allows multiple answers, ignored for polls in quiz mode, defaults to <em>False</em></td>
</tr>
<tr>
<td>correct_option_id</td>
<td>Integer</td>
<td>Optional</td>
<td>0-based identifier of the correct answer option, required for polls in quiz mode</td>
</tr>
<tr>
<td>explanation</td>
<td>String</td>
<td>Optional</td>
<td>Text that is shown when a user chooses an incorrect answer or taps on the lamp icon in a quiz-style poll, 0-200 characters with at most 2 line feeds after entities parsing</td>
</tr>
<tr>
<td>explanation_parse_mode</td>
<td>String</td>
<td>Optional</td>
<td>Mode for parsing entities in the explanation. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>explanation_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td>Optional</td>
<td>A JSON-serialized list of special entities that appear in the poll explanation, which can be specified instead of <em>parse_mode</em></td>
</tr>
<tr>
<td>open_period</td>
<td>Integer</td>
<td>Optional</td>
<td>Amount of time in seconds the poll will be active after creation, 5-600. Can&#39;t be used together with <em>close_date</em>.</td>
</tr>
<tr>
<td>close_date</td>
<td>Integer</td>
<td>Optional</td>
<td>Point in time (Unix timestamp) when the poll will be automatically closed. Must be at least 5 and no more than 600 seconds in the future. Can&#39;t be used together with <em>open_period</em>.</td>
</tr>
<tr>
<td>is_closed</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the poll needs to be immediately closed. This can be useful for poll preview.</td>
</tr>
<tr>
<td>disable_notification</td>
<td>Boolean</td>
<td>Optional</td>
<td>Sends the message <a href="https://telegram.org/blog/channels-2-0#silent-messages">silently</a>. Users will receive a notification with no sound.</td>
</tr>
<tr>
<td>protect_content</td>
<td>Boolean</td>
<td>Optional</td>
<td>Protects the contents of the sent message from forwarding and saving</td>
</tr>
<tr>
<td>reply_to_message_id</td>
<td>Integer</td>
<td>Optional</td>
<td>If the message is a reply, ID of the original message</td>
</tr>
<tr>
<td>allow_sending_without_reply</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the message should be sent even if the specified replied-to message is not found</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a> or <a href="#replykeyboardmarkup">ReplyKeyboardMarkup</a> or <a href="#replykeyboardremove">ReplyKeyboardRemove</a> or <a href="#forcereply">ForceReply</a></td>
<td>Optional</td>
<td>Additional interface options. A JSON-serialized object for an <a href="https://core.telegram.org/bots#inline-keyboards-and-on-the-fly-updating">inline keyboard</a>, <a href="https://core.telegram.org/bots#keyboards">custom reply keyboard</a>, instructions to remove reply keyboard or to force a reply from the user.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="senddice" href="#senddice"><i class="anchor-icon"></i></a>sendDice</h4>
<p>Use this method to send an animated emoji that will display a random value. On success, the sent <a href="#message">Message</a> is returned.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>emoji</td>
<td>String</td>
<td>Optional</td>
<td>Emoji on which the dice throw animation is based. Currently, must be one of “<img class="emoji" src="//telegram.org/img/emoji/40/F09F8EB2.png" width="20" height="20" alt="🎲" />”, “<img class="emoji" src="//telegram.org/img/emoji/40/F09F8EAF.png" width="20" height="20" alt="🎯" />”, “<img class="emoji" src="//telegram.org/img/emoji/40/F09F8F80.png" width="20" height="20" alt="🏀" />”, “<img class="emoji" src="//telegram.org/img/emoji/40/E29ABD.png" width="20" height="20" alt="⚽" />”, “<img class="emoji" src="//telegram.org/img/emoji/40/F09F8EB3.png" width="20" height="20" alt="🎳" />”, or “<img class="emoji" src="//telegram.org/img/emoji/40/F09F8EB0.png" width="20" height="20" alt="🎰" />”. Dice can have values 1-6 for “<img class="emoji" src="//telegram.org/img/emoji/40/F09F8EB2.png" width="20" height="20" alt="🎲" />”, “<img class="emoji" src="//telegram.org/img/emoji/40/F09F8EAF.png" width="20" height="20" alt="🎯" />” and “<img class="emoji" src="//telegram.org/img/emoji/40/F09F8EB3.png" width="20" height="20" alt="🎳" />”, values 1-5 for “<img class="emoji" src="//telegram.org/img/emoji/40/F09F8F80.png" width="20" height="20" alt="🏀" />” and “<img class="emoji" src="//telegram.org/img/emoji/40/E29ABD.png" width="20" height="20" alt="⚽" />”, and values 1-64 for “<img class="emoji" src="//telegram.org/img/emoji/40/F09F8EB0.png" width="20" height="20" alt="🎰" />”. Defaults to “<img class="emoji" src="//telegram.org/img/emoji/40/F09F8EB2.png" width="20" height="20" alt="🎲" />”</td>
</tr>
<tr>
<td>disable_notification</td>
<td>Boolean</td>
<td>Optional</td>
<td>Sends the message <a href="https://telegram.org/blog/channels-2-0#silent-messages">silently</a>. Users will receive a notification with no sound.</td>
</tr>
<tr>
<td>protect_content</td>
<td>Boolean</td>
<td>Optional</td>
<td>Protects the contents of the sent message from forwarding</td>
</tr>
<tr>
<td>reply_to_message_id</td>
<td>Integer</td>
<td>Optional</td>
<td>If the message is a reply, ID of the original message</td>
</tr>
<tr>
<td>allow_sending_without_reply</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the message should be sent even if the specified replied-to message is not found</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a> or <a href="#replykeyboardmarkup">ReplyKeyboardMarkup</a> or <a href="#replykeyboardremove">ReplyKeyboardRemove</a> or <a href="#forcereply">ForceReply</a></td>
<td>Optional</td>
<td>Additional interface options. A JSON-serialized object for an <a href="https://core.telegram.org/bots#inline-keyboards-and-on-the-fly-updating">inline keyboard</a>, <a href="https://core.telegram.org/bots#keyboards">custom reply keyboard</a>, instructions to remove reply keyboard or to force a reply from the user.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="sendchataction" href="#sendchataction"><i class="anchor-icon"></i></a>sendChatAction</h4>
<p>Use this method when you need to tell the user that something is happening on the bot&#39;s side. The status is set for 5 seconds or less (when a message arrives from your bot, Telegram clients clear its typing status). Returns <em>True</em> on success.</p>
<blockquote>
<p>Example: The <a href="https://t.me/imagebot">ImageBot</a> needs some time to process a request and upload the image. Instead of sending a text message along the lines of “Retrieving image, please wait…”, the bot may use <a href="#sendchataction">sendChatAction</a> with <em>action</em> = <em>upload_photo</em>. The user will see a “sending photo” status for the bot.</p>
</blockquote>
<p>We only recommend using this method when a response from the bot will take a <strong>noticeable</strong> amount of time to arrive.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>action</td>
<td>String</td>
<td>Yes</td>
<td>Type of action to broadcast. Choose one, depending on what the user is about to receive: <em>typing</em> for <a href="#sendmessage">text messages</a>, <em>upload_photo</em> for <a href="#sendphoto">photos</a>, <em>record_video</em> or <em>upload_video</em> for <a href="#sendvideo">videos</a>, <em>record_voice</em> or <em>upload_voice</em> for <a href="#sendvoice">voice notes</a>, <em>upload_document</em> for <a href="#senddocument">general files</a>, <em>choose_sticker</em> for <a href="#sendsticker">stickers</a>, <em>find_location</em> for <a href="#sendlocation">location data</a>, <em>record_video_note</em> or <em>upload_video_note</em> for <a href="#sendvideonote">video notes</a>.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="getuserprofilephotos" href="#getuserprofilephotos"><i class="anchor-icon"></i></a>getUserProfilePhotos</h4>
<p>Use this method to get a list of profile pictures for a user. Returns a <a href="#userprofilephotos">UserProfilePhotos</a> object.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>user_id</td>
<td>Integer</td>
<td>Yes</td>
<td>Unique identifier of the target user</td>
</tr>
<tr>
<td>offset</td>
<td>Integer</td>
<td>Optional</td>
<td>Sequential number of the first photo to be returned. By default, all photos are returned.</td>
</tr>
<tr>
<td>limit</td>
<td>Integer</td>
<td>Optional</td>
<td>Limits the number of photos to be retrieved. Values between 1-100 are accepted. Defaults to 100.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="getfile" href="#getfile"><i class="anchor-icon"></i></a>getFile</h4>
<p>Use this method to get basic info about a file and prepare it for downloading. For the moment, bots can download files of up to 20MB in size. On success, a <a href="#file">File</a> object is returned. The file can then be downloaded via the link <code>https://api.telegram.org/file/bot&lt;token&gt;/&lt;file_path&gt;</code>, where <code>&lt;file_path&gt;</code> is taken from the response. It is guaranteed that the link will be valid for at least 1 hour. When the link expires, a new one can be requested by calling <a href="#getfile">getFile</a> again.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>file_id</td>
<td>String</td>
<td>Yes</td>
<td>File identifier to get info about</td>
</tr>
</tbody>
</table>
<p><strong>Note:</strong> This function may not preserve the original file name and MIME type. You should save the file&#39;s MIME type and name (if available) when the File object is received.</p>
<h4><a class="anchor" name="banchatmember" href="#banchatmember"><i class="anchor-icon"></i></a>banChatMember</h4>
<p>Use this method to ban a user in a group, a supergroup or a channel. In the case of supergroups and channels, the user will not be able to return to the chat on their own using invite links, etc., unless <a href="#unbanchatmember">unbanned</a> first. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Returns <em>True</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target group or username of the target supergroup or channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>user_id</td>
<td>Integer</td>
<td>Yes</td>
<td>Unique identifier of the target user</td>
</tr>
<tr>
<td>until_date</td>
<td>Integer</td>
<td>Optional</td>
<td>Date when the user will be unbanned, unix time. If user is banned for more than 366 days or less than 30 seconds from the current time they are considered to be banned forever. Applied for supergroups and channels only.</td>
</tr>
<tr>
<td>revoke_messages</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em> to delete all messages from the chat for the user that is being removed. If <em>False</em>, the user will be able to see messages in the group that were sent before the user was removed. Always <em>True</em> for supergroups and channels.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="unbanchatmember" href="#unbanchatmember"><i class="anchor-icon"></i></a>unbanChatMember</h4>
<p>Use this method to unban a previously banned user in a supergroup or channel. The user will <strong>not</strong> return to the group or channel automatically, but will be able to join via link, etc. The bot must be an administrator for this to work. By default, this method guarantees that after the call the user is not a member of the chat, but will be able to join it. So if the user is a member of the chat they will also be <strong>removed</strong> from the chat. If you don&#39;t want this, use the parameter <em>only_if_banned</em>. Returns <em>True</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target group or username of the target supergroup or channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>user_id</td>
<td>Integer</td>
<td>Yes</td>
<td>Unique identifier of the target user</td>
</tr>
<tr>
<td>only_if_banned</td>
<td>Boolean</td>
<td>Optional</td>
<td>Do nothing if the user is not banned</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="restrictchatmember" href="#restrictchatmember"><i class="anchor-icon"></i></a>restrictChatMember</h4>
<p>Use this method to restrict a user in a supergroup. The bot must be an administrator in the supergroup for this to work and must have the appropriate administrator rights. Pass <em>True</em> for all permissions to lift restrictions from a user. Returns <em>True</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target supergroup (in the format <code>@supergroupusername</code>)</td>
</tr>
<tr>
<td>user_id</td>
<td>Integer</td>
<td>Yes</td>
<td>Unique identifier of the target user</td>
</tr>
<tr>
<td>permissions</td>
<td><a href="#chatpermissions">ChatPermissions</a></td>
<td>Yes</td>
<td>A JSON-serialized object for new user permissions</td>
</tr>
<tr>
<td>until_date</td>
<td>Integer</td>
<td>Optional</td>
<td>Date when restrictions will be lifted for the user, unix time. If user is restricted for more than 366 days or less than 30 seconds from the current time, they are considered to be restricted forever</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="promotechatmember" href="#promotechatmember"><i class="anchor-icon"></i></a>promoteChatMember</h4>
<p>Use this method to promote or demote a user in a supergroup or a channel. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Pass <em>False</em> for all boolean parameters to demote a user. Returns <em>True</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>user_id</td>
<td>Integer</td>
<td>Yes</td>
<td>Unique identifier of the target user</td>
</tr>
<tr>
<td>is_anonymous</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the administrator&#39;s presence in the chat is hidden</td>
</tr>
<tr>
<td>can_manage_chat</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the administrator can access the chat event log, chat statistics, message statistics in channels, see channel members, see anonymous administrators in supergroups and ignore slow mode. Implied by any other administrator privilege</td>
</tr>
<tr>
<td>can_post_messages</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the administrator can create channel posts, channels only</td>
</tr>
<tr>
<td>can_edit_messages</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the administrator can edit messages of other users and can pin messages, channels only</td>
</tr>
<tr>
<td>can_delete_messages</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the administrator can delete messages of other users</td>
</tr>
<tr>
<td>can_manage_voice_chats</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the administrator can manage voice chats</td>
</tr>
<tr>
<td>can_restrict_members</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the administrator can restrict, ban or unban chat members</td>
</tr>
<tr>
<td>can_promote_members</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the administrator can add new administrators with a subset of their own privileges or demote administrators that he has promoted, directly or indirectly (promoted by administrators that were appointed by him)</td>
</tr>
<tr>
<td>can_change_info</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the administrator can change chat title, photo and other settings</td>
</tr>
<tr>
<td>can_invite_users</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the administrator can invite new users to the chat</td>
</tr>
<tr>
<td>can_pin_messages</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the administrator can pin messages, supergroups only</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="setchatadministratorcustomtitle" href="#setchatadministratorcustomtitle"><i class="anchor-icon"></i></a>setChatAdministratorCustomTitle</h4>
<p>Use this method to set a custom title for an administrator in a supergroup promoted by the bot. Returns <em>True</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target supergroup (in the format <code>@supergroupusername</code>)</td>
</tr>
<tr>
<td>user_id</td>
<td>Integer</td>
<td>Yes</td>
<td>Unique identifier of the target user</td>
</tr>
<tr>
<td>custom_title</td>
<td>String</td>
<td>Yes</td>
<td>New custom title for the administrator; 0-16 characters, emoji are not allowed</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="banchatsenderchat" href="#banchatsenderchat"><i class="anchor-icon"></i></a>banChatSenderChat</h4>
<p>Use this method to ban a channel chat in a supergroup or a channel. Until the chat is <a href="#unbanchatsenderchat">unbanned</a>, the owner of the banned chat won&#39;t be able to send messages on behalf of <strong>any of their channels</strong>. The bot must be an administrator in the supergroup or channel for this to work and must have the appropriate administrator rights. Returns <em>True</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>sender_chat_id</td>
<td>Integer</td>
<td>Yes</td>
<td>Unique identifier of the target sender chat</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="unbanchatsenderchat" href="#unbanchatsenderchat"><i class="anchor-icon"></i></a>unbanChatSenderChat</h4>
<p>Use this method to unban a previously banned channel chat in a supergroup or channel. The bot must be an administrator for this to work and must have the appropriate administrator rights. Returns <em>True</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>sender_chat_id</td>
<td>Integer</td>
<td>Yes</td>
<td>Unique identifier of the target sender chat</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="setchatpermissions" href="#setchatpermissions"><i class="anchor-icon"></i></a>setChatPermissions</h4>
<p>Use this method to set default chat permissions for all members. The bot must be an administrator in the group or a supergroup for this to work and must have the <em>can_restrict_members</em> administrator rights. Returns <em>True</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target supergroup (in the format <code>@supergroupusername</code>)</td>
</tr>
<tr>
<td>permissions</td>
<td><a href="#chatpermissions">ChatPermissions</a></td>
<td>Yes</td>
<td>A JSON-serialized object for new default chat permissions</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="exportchatinvitelink" href="#exportchatinvitelink"><i class="anchor-icon"></i></a>exportChatInviteLink</h4>
<p>Use this method to generate a new primary invite link for a chat; any previously generated primary link is revoked. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Returns the new invite link as <em>String</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
</tbody>
</table>
<blockquote>
<p>Note: Each administrator in a chat generates their own invite links. Bots can&#39;t use invite links generated by other administrators. If you want your bot to work with invite links, it will need to generate its own link using <a href="#exportchatinvitelink">exportChatInviteLink</a> or by calling the <a href="#getchat">getChat</a> method. If your bot needs to generate a new primary invite link replacing its previous one, use <a href="#exportchatinvitelink">exportChatInviteLink</a> again.</p>
</blockquote>
<h4><a class="anchor" name="createchatinvitelink" href="#createchatinvitelink"><i class="anchor-icon"></i></a>createChatInviteLink</h4>
<p>Use this method to create an additional invite link for a chat. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. The link can be revoked using the method <a href="#revokechatinvitelink">revokeChatInviteLink</a>. Returns the new invite link as <a href="#chatinvitelink">ChatInviteLink</a> object.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>name</td>
<td>String</td>
<td>Optional</td>
<td>Invite link name; 0-32 characters</td>
</tr>
<tr>
<td>expire_date</td>
<td>Integer</td>
<td>Optional</td>
<td>Point in time (Unix timestamp) when the link will expire</td>
</tr>
<tr>
<td>member_limit</td>
<td>Integer</td>
<td>Optional</td>
<td>Maximum number of users that can be members of the chat simultaneously after joining the chat via this invite link; 1-99999</td>
</tr>
<tr>
<td>creates_join_request</td>
<td>Boolean</td>
<td>Optional</td>
<td><em>True</em>, if users joining the chat via the link need to be approved by chat administrators. If <em>True</em>, <em>member_limit</em> can&#39;t be specified</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="editchatinvitelink" href="#editchatinvitelink"><i class="anchor-icon"></i></a>editChatInviteLink</h4>
<p>Use this method to edit a non-primary invite link created by the bot. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Returns the edited invite link as a <a href="#chatinvitelink">ChatInviteLink</a> object.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>invite_link</td>
<td>String</td>
<td>Yes</td>
<td>The invite link to edit</td>
</tr>
<tr>
<td>name</td>
<td>String</td>
<td>Optional</td>
<td>Invite link name; 0-32 characters</td>
</tr>
<tr>
<td>expire_date</td>
<td>Integer</td>
<td>Optional</td>
<td>Point in time (Unix timestamp) when the link will expire</td>
</tr>
<tr>
<td>member_limit</td>
<td>Integer</td>
<td>Optional</td>
<td>Maximum number of users that can be members of the chat simultaneously after joining the chat via this invite link; 1-99999</td>
</tr>
<tr>
<td>creates_join_request</td>
<td>Boolean</td>
<td>Optional</td>
<td><em>True</em>, if users joining the chat via the link need to be approved by chat administrators. If <em>True</em>, <em>member_limit</em> can&#39;t be specified</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="revokechatinvitelink" href="#revokechatinvitelink"><i class="anchor-icon"></i></a>revokeChatInviteLink</h4>
<p>Use this method to revoke an invite link created by the bot. If the primary link is revoked, a new link is automatically generated. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Returns the revoked invite link as <a href="#chatinvitelink">ChatInviteLink</a> object.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier of the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>invite_link</td>
<td>String</td>
<td>Yes</td>
<td>The invite link to revoke</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="approvechatjoinrequest" href="#approvechatjoinrequest"><i class="anchor-icon"></i></a>approveChatJoinRequest</h4>
<p>Use this method to approve a chat join request. The bot must be an administrator in the chat for this to work and must have the <em>can_invite_users</em> administrator right. Returns <em>True</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>user_id</td>
<td>Integer</td>
<td>Yes</td>
<td>Unique identifier of the target user</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="declinechatjoinrequest" href="#declinechatjoinrequest"><i class="anchor-icon"></i></a>declineChatJoinRequest</h4>
<p>Use this method to decline a chat join request. The bot must be an administrator in the chat for this to work and must have the <em>can_invite_users</em> administrator right. Returns <em>True</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>user_id</td>
<td>Integer</td>
<td>Yes</td>
<td>Unique identifier of the target user</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="setchatphoto" href="#setchatphoto"><i class="anchor-icon"></i></a>setChatPhoto</h4>
<p>Use this method to set a new profile photo for the chat. Photos can&#39;t be changed for private chats. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Returns <em>True</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>photo</td>
<td><a href="#inputfile">InputFile</a></td>
<td>Yes</td>
<td>New chat photo, uploaded using multipart/form-data</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="deletechatphoto" href="#deletechatphoto"><i class="anchor-icon"></i></a>deleteChatPhoto</h4>
<p>Use this method to delete a chat photo. Photos can&#39;t be changed for private chats. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Returns <em>True</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="setchattitle" href="#setchattitle"><i class="anchor-icon"></i></a>setChatTitle</h4>
<p>Use this method to change the title of a chat. Titles can&#39;t be changed for private chats. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Returns <em>True</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>title</td>
<td>String</td>
<td>Yes</td>
<td>New chat title, 1-255 characters</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="setchatdescription" href="#setchatdescription"><i class="anchor-icon"></i></a>setChatDescription</h4>
<p>Use this method to change the description of a group, a supergroup or a channel. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Returns <em>True</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>description</td>
<td>String</td>
<td>Optional</td>
<td>New chat description, 0-255 characters</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="pinchatmessage" href="#pinchatmessage"><i class="anchor-icon"></i></a>pinChatMessage</h4>
<p>Use this method to add a message to the list of pinned messages in a chat. If the chat is not a private chat, the bot must be an administrator in the chat for this to work and must have the &#39;can_pin_messages&#39; administrator right in a supergroup or &#39;can_edit_messages&#39; administrator right in a channel. Returns <em>True</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>message_id</td>
<td>Integer</td>
<td>Yes</td>
<td>Identifier of a message to pin</td>
</tr>
<tr>
<td>disable_notification</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if it is not necessary to send a notification to all chat members about the new pinned message. Notifications are always disabled in channels and private chats.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="unpinchatmessage" href="#unpinchatmessage"><i class="anchor-icon"></i></a>unpinChatMessage</h4>
<p>Use this method to remove a message from the list of pinned messages in a chat. If the chat is not a private chat, the bot must be an administrator in the chat for this to work and must have the &#39;can_pin_messages&#39; administrator right in a supergroup or &#39;can_edit_messages&#39; administrator right in a channel. Returns <em>True</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>message_id</td>
<td>Integer</td>
<td>Optional</td>
<td>Identifier of a message to unpin. If not specified, the most recent pinned message (by sending date) will be unpinned.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="unpinallchatmessages" href="#unpinallchatmessages"><i class="anchor-icon"></i></a>unpinAllChatMessages</h4>
<p>Use this method to clear the list of pinned messages in a chat. If the chat is not a private chat, the bot must be an administrator in the chat for this to work and must have the &#39;can_pin_messages&#39; administrator right in a supergroup or &#39;can_edit_messages&#39; administrator right in a channel. Returns <em>True</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="leavechat" href="#leavechat"><i class="anchor-icon"></i></a>leaveChat</h4>
<p>Use this method for your bot to leave a group, supergroup or channel. Returns <em>True</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target supergroup or channel (in the format <code>@channelusername</code>)</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="getchat" href="#getchat"><i class="anchor-icon"></i></a>getChat</h4>
<p>Use this method to get up to date information about the chat (current name of the user for one-on-one conversations, current username of a user, group or channel, etc.). Returns a <a href="#chat">Chat</a> object on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target supergroup or channel (in the format <code>@channelusername</code>)</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="getchatadministrators" href="#getchatadministrators"><i class="anchor-icon"></i></a>getChatAdministrators</h4>
<p>Use this method to get a list of administrators in a chat. On success, returns an Array of <a href="#chatmember">ChatMember</a> objects that contains information about all chat administrators except other bots. If the chat is a group or a supergroup and no administrators were appointed, only the creator will be returned.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target supergroup or channel (in the format <code>@channelusername</code>)</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="getchatmembercount" href="#getchatmembercount"><i class="anchor-icon"></i></a>getChatMemberCount</h4>
<p>Use this method to get the number of members in a chat. Returns <em>Int</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target supergroup or channel (in the format <code>@channelusername</code>)</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="getchatmember" href="#getchatmember"><i class="anchor-icon"></i></a>getChatMember</h4>
<p>Use this method to get information about a member of a chat. Returns a <a href="#chatmember">ChatMember</a> object on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target supergroup or channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>user_id</td>
<td>Integer</td>
<td>Yes</td>
<td>Unique identifier of the target user</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="setchatstickerset" href="#setchatstickerset"><i class="anchor-icon"></i></a>setChatStickerSet</h4>
<p>Use this method to set a new group sticker set for a supergroup. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Use the field <em>can_set_sticker_set</em> optionally returned in <a href="#getchat">getChat</a> requests to check if the bot can use this method. Returns <em>True</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target supergroup (in the format <code>@supergroupusername</code>)</td>
</tr>
<tr>
<td>sticker_set_name</td>
<td>String</td>
<td>Yes</td>
<td>Name of the sticker set to be set as the group sticker set</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="deletechatstickerset" href="#deletechatstickerset"><i class="anchor-icon"></i></a>deleteChatStickerSet</h4>
<p>Use this method to delete a group sticker set from a supergroup. The bot must be an administrator in the chat for this to work and must have the appropriate administrator rights. Use the field <em>can_set_sticker_set</em> optionally returned in <a href="#getchat">getChat</a> requests to check if the bot can use this method. Returns <em>True</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target supergroup (in the format <code>@supergroupusername</code>)</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="answercallbackquery" href="#answercallbackquery"><i class="anchor-icon"></i></a>answerCallbackQuery</h4>
<p>Use this method to send answers to callback queries sent from <a href="/bots#inline-keyboards-and-on-the-fly-updating">inline keyboards</a>. The answer will be displayed to the user as a notification at the top of the chat screen or as an alert. On success, <em>True</em> is returned.</p>
<blockquote>
<p>Alternatively, the user can be redirected to the specified Game URL. For this option to work, you must first create a game for your bot via <a href="https://t.me/botfather">@Botfather</a> and accept the terms. Otherwise, you may use links like <code>t.me/your_bot?start=XXXX</code> that open your bot with a parameter.</p>
</blockquote>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>callback_query_id</td>
<td>String</td>
<td>Yes</td>
<td>Unique identifier for the query to be answered</td>
</tr>
<tr>
<td>text</td>
<td>String</td>
<td>Optional</td>
<td>Text of the notification. If not specified, nothing will be shown to the user, 0-200 characters</td>
</tr>
<tr>
<td>show_alert</td>
<td>Boolean</td>
<td>Optional</td>
<td>If <em>True</em>, an alert will be shown by the client instead of a notification at the top of the chat screen. Defaults to <em>false</em>.</td>
</tr>
<tr>
<td>url</td>
<td>String</td>
<td>Optional</td>
<td>URL that will be opened by the user&#39;s client. If you have created a <a href="#game">Game</a> and accepted the conditions via <a href="https://t.me/botfather">@Botfather</a>, specify the URL that opens your game — note that this will only work if the query comes from a <a href="#inlinekeyboardbutton"><em>callback_game</em></a> button.<br><br>Otherwise, you may use links like <code>t.me/your_bot?start=XXXX</code> that open your bot with a parameter.</td>
</tr>
<tr>
<td>cache_time</td>
<td>Integer</td>
<td>Optional</td>
<td>The maximum amount of time in seconds that the result of the callback query may be cached client-side. Telegram apps will support caching starting in version 3.14. Defaults to 0.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="setmycommands" href="#setmycommands"><i class="anchor-icon"></i></a>setMyCommands</h4>
<p>Use this method to change the list of the bot&#39;s commands. See <a href="https://core.telegram.org/bots#commands"><a href="https://core.telegram.org/bots#commands">https://core.telegram.org/bots#commands</a></a> for more details about bot commands. Returns <em>True</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>commands</td>
<td>Array of <a href="#botcommand">BotCommand</a></td>
<td>Yes</td>
<td>A JSON-serialized list of bot commands to be set as the list of the bot&#39;s commands. At most 100 commands can be specified.</td>
</tr>
<tr>
<td>scope</td>
<td><a href="#botcommandscope">BotCommandScope</a></td>
<td>Optional</td>
<td>A JSON-serialized object, describing scope of users for which the commands are relevant. Defaults to <a href="#botcommandscopedefault">BotCommandScopeDefault</a>.</td>
</tr>
<tr>
<td>language_code</td>
<td>String</td>
<td>Optional</td>
<td>A two-letter ISO 639-1 language code. If empty, commands will be applied to all users from the given scope, for whose language there are no dedicated commands</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="deletemycommands" href="#deletemycommands"><i class="anchor-icon"></i></a>deleteMyCommands</h4>
<p>Use this method to delete the list of the bot&#39;s commands for the given scope and user language. After deletion, <a href="#determining-list-of-commands">higher level commands</a> will be shown to affected users. Returns <em>True</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>scope</td>
<td><a href="#botcommandscope">BotCommandScope</a></td>
<td>Optional</td>
<td>A JSON-serialized object, describing scope of users for which the commands are relevant. Defaults to <a href="#botcommandscopedefault">BotCommandScopeDefault</a>.</td>
</tr>
<tr>
<td>language_code</td>
<td>String</td>
<td>Optional</td>
<td>A two-letter ISO 639-1 language code. If empty, commands will be applied to all users from the given scope, for whose language there are no dedicated commands</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="getmycommands" href="#getmycommands"><i class="anchor-icon"></i></a>getMyCommands</h4>
<p>Use this method to get the current list of the bot&#39;s commands for the given scope and user language. Returns Array of <a href="#botcommand">BotCommand</a> on success. If commands aren&#39;t set, an empty list is returned.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>scope</td>
<td><a href="#botcommandscope">BotCommandScope</a></td>
<td>Optional</td>
<td>A JSON-serialized object, describing scope of users. Defaults to <a href="#botcommandscopedefault">BotCommandScopeDefault</a>.</td>
</tr>
<tr>
<td>language_code</td>
<td>String</td>
<td>Optional</td>
<td>A two-letter ISO 639-1 language code or an empty string</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="inline-mode-methods" href="#inline-mode-methods"><i class="anchor-icon"></i></a>Inline mode methods</h4>
<p>Methods and objects used in the inline mode are described in the <a href="#inline-mode">Inline mode section</a>.</p>
<h3><a class="anchor" name="updating-messages" href="#updating-messages"><i class="anchor-icon"></i></a>Updating messages</h3>
<p>The following methods allow you to change an existing message in the message history instead of sending a new one with a result of an action. This is most useful for messages with <a href="/bots#inline-keyboards-and-on-the-fly-updating">inline keyboards</a> using callback queries, but can also help reduce clutter in conversations with regular chat bots.</p>
<p>Please note, that it is currently only possible to edit messages without <em>reply_markup</em> or with <a href="/bots#inline-keyboards-and-on-the-fly-updating">inline keyboards</a>.</p>
<h4><a class="anchor" name="editmessagetext" href="#editmessagetext"><i class="anchor-icon"></i></a>editMessageText</h4>
<p>Use this method to edit text and <a href="#games">game</a> messages. On success, if the edited message is not an inline message, the edited <a href="#message">Message</a> is returned, otherwise <em>True</em> is returned.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Optional</td>
<td>Required if <em>inline_message_id</em> is not specified. Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>message_id</td>
<td>Integer</td>
<td>Optional</td>
<td>Required if <em>inline_message_id</em> is not specified. Identifier of the message to edit</td>
</tr>
<tr>
<td>inline_message_id</td>
<td>String</td>
<td>Optional</td>
<td>Required if <em>chat_id</em> and <em>message_id</em> are not specified. Identifier of the inline message</td>
</tr>
<tr>
<td>text</td>
<td>String</td>
<td>Yes</td>
<td>New text of the message, 1-4096 characters after entities parsing</td>
</tr>
<tr>
<td>parse_mode</td>
<td>String</td>
<td>Optional</td>
<td>Mode for parsing entities in the message text. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td>Optional</td>
<td>A JSON-serialized list of special entities that appear in message text, which can be specified instead of <em>parse_mode</em></td>
</tr>
<tr>
<td>disable_web_page_preview</td>
<td>Boolean</td>
<td>Optional</td>
<td>Disables link previews for links in this message</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a></td>
<td>Optional</td>
<td>A JSON-serialized object for an <a href="https://core.telegram.org/bots#inline-keyboards-and-on-the-fly-updating">inline keyboard</a>.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="editmessagecaption" href="#editmessagecaption"><i class="anchor-icon"></i></a>editMessageCaption</h4>
<p>Use this method to edit captions of messages. On success, if the edited message is not an inline message, the edited <a href="#message">Message</a> is returned, otherwise <em>True</em> is returned.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Optional</td>
<td>Required if <em>inline_message_id</em> is not specified. Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>message_id</td>
<td>Integer</td>
<td>Optional</td>
<td>Required if <em>inline_message_id</em> is not specified. Identifier of the message to edit</td>
</tr>
<tr>
<td>inline_message_id</td>
<td>String</td>
<td>Optional</td>
<td>Required if <em>chat_id</em> and <em>message_id</em> are not specified. Identifier of the inline message</td>
</tr>
<tr>
<td>caption</td>
<td>String</td>
<td>Optional</td>
<td>New caption of the message, 0-1024 characters after entities parsing</td>
</tr>
<tr>
<td>parse_mode</td>
<td>String</td>
<td>Optional</td>
<td>Mode for parsing entities in the message caption. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>caption_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td>Optional</td>
<td>A JSON-serialized list of special entities that appear in the caption, which can be specified instead of <em>parse_mode</em></td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a></td>
<td>Optional</td>
<td>A JSON-serialized object for an <a href="https://core.telegram.org/bots#inline-keyboards-and-on-the-fly-updating">inline keyboard</a>.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="editmessagemedia" href="#editmessagemedia"><i class="anchor-icon"></i></a>editMessageMedia</h4>
<p>Use this method to edit animation, audio, document, photo, or video messages. If a message is part of a message album, then it can be edited only to an audio for audio albums, only to a document for document albums and to a photo or a video otherwise. When an inline message is edited, a new file can&#39;t be uploaded; use a previously uploaded file via its file_id or specify a URL. On success, if the edited message is not an inline message, the edited <a href="#message">Message</a> is returned, otherwise <em>True</em> is returned.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Optional</td>
<td>Required if <em>inline_message_id</em> is not specified. Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>message_id</td>
<td>Integer</td>
<td>Optional</td>
<td>Required if <em>inline_message_id</em> is not specified. Identifier of the message to edit</td>
</tr>
<tr>
<td>inline_message_id</td>
<td>String</td>
<td>Optional</td>
<td>Required if <em>chat_id</em> and <em>message_id</em> are not specified. Identifier of the inline message</td>
</tr>
<tr>
<td>media</td>
<td><a href="#inputmedia">InputMedia</a></td>
<td>Yes</td>
<td>A JSON-serialized object for a new media content of the message</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a></td>
<td>Optional</td>
<td>A JSON-serialized object for a new <a href="https://core.telegram.org/bots#inline-keyboards-and-on-the-fly-updating">inline keyboard</a>.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="editmessagereplymarkup" href="#editmessagereplymarkup"><i class="anchor-icon"></i></a>editMessageReplyMarkup</h4>
<p>Use this method to edit only the reply markup of messages. On success, if the edited message is not an inline message, the edited <a href="#message">Message</a> is returned, otherwise <em>True</em> is returned.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Optional</td>
<td>Required if <em>inline_message_id</em> is not specified. Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>message_id</td>
<td>Integer</td>
<td>Optional</td>
<td>Required if <em>inline_message_id</em> is not specified. Identifier of the message to edit</td>
</tr>
<tr>
<td>inline_message_id</td>
<td>String</td>
<td>Optional</td>
<td>Required if <em>chat_id</em> and <em>message_id</em> are not specified. Identifier of the inline message</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a></td>
<td>Optional</td>
<td>A JSON-serialized object for an <a href="https://core.telegram.org/bots#inline-keyboards-and-on-the-fly-updating">inline keyboard</a>.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="stoppoll" href="#stoppoll"><i class="anchor-icon"></i></a>stopPoll</h4>
<p>Use this method to stop a poll which was sent by the bot. On success, the stopped <a href="#poll">Poll</a> is returned.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>message_id</td>
<td>Integer</td>
<td>Yes</td>
<td>Identifier of the original message with the poll</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a></td>
<td>Optional</td>
<td>A JSON-serialized object for a new message <a href="https://core.telegram.org/bots#inline-keyboards-and-on-the-fly-updating">inline keyboard</a>.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="deletemessage" href="#deletemessage"><i class="anchor-icon"></i></a>deleteMessage</h4>
<p>Use this method to delete a message, including service messages, with the following limitations:<br>- A message can only be deleted if it was sent less than 48 hours ago.<br>- A dice message in a private chat can only be deleted if it was sent more than 24 hours ago.<br>- Bots can delete outgoing messages in private chats, groups, and supergroups.<br>- Bots can delete incoming messages in private chats.<br>- Bots granted <em>can_post_messages</em> permissions can delete outgoing messages in channels.<br>- If the bot is an administrator of a group, it can delete any message there.<br>- If the bot has <em>can_delete_messages</em> permission in a supergroup or a channel, it can delete any message there.<br>Returns <em>True</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>message_id</td>
<td>Integer</td>
<td>Yes</td>
<td>Identifier of the message to delete</td>
</tr>
</tbody>
</table>
<h3><a class="anchor" name="stickers" href="#stickers"><i class="anchor-icon"></i></a>Stickers</h3>
<p>The following methods and objects allow your bot to handle stickers and sticker sets.</p>
<h4><a class="anchor" name="sticker" href="#sticker"><i class="anchor-icon"></i></a>Sticker</h4>
<p>This object represents a sticker.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>file_id</td>
<td>String</td>
<td>Identifier for this file, which can be used to download or reuse the file</td>
</tr>
<tr>
<td>file_unique_id</td>
<td>String</td>
<td>Unique identifier for this file, which is supposed to be the same over time and for different bots. Can&#39;t be used to download or reuse the file.</td>
</tr>
<tr>
<td>width</td>
<td>Integer</td>
<td>Sticker width</td>
</tr>
<tr>
<td>height</td>
<td>Integer</td>
<td>Sticker height</td>
</tr>
<tr>
<td>is_animated</td>
<td>Boolean</td>
<td><em>True</em>, if the sticker is <a href="https://telegram.org/blog/animated-stickers">animated</a></td>
</tr>
<tr>
<td>is_video</td>
<td>Boolean</td>
<td><em>True</em>, if the sticker is a <a href="https://telegram.org/blog/video-stickers-better-reactions">video sticker</a></td>
</tr>
<tr>
<td>thumb</td>
<td><a href="#photosize">PhotoSize</a></td>
<td><em>Optional</em>. Sticker thumbnail in the .WEBP or .JPG format</td>
</tr>
<tr>
<td>emoji</td>
<td>String</td>
<td><em>Optional</em>. Emoji associated with the sticker</td>
</tr>
<tr>
<td>set_name</td>
<td>String</td>
<td><em>Optional</em>. Name of the sticker set to which the sticker belongs</td>
</tr>
<tr>
<td>mask_position</td>
<td><a href="#maskposition">MaskPosition</a></td>
<td><em>Optional</em>. For mask stickers, the position where the mask should be placed</td>
</tr>
<tr>
<td>file_size</td>
<td>Integer</td>
<td><em>Optional</em>. File size in bytes</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="stickerset" href="#stickerset"><i class="anchor-icon"></i></a>StickerSet</h4>
<p>This object represents a sticker set.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>name</td>
<td>String</td>
<td>Sticker set name</td>
</tr>
<tr>
<td>title</td>
<td>String</td>
<td>Sticker set title</td>
</tr>
<tr>
<td>is_animated</td>
<td>Boolean</td>
<td><em>True</em>, if the sticker set contains <a href="https://telegram.org/blog/animated-stickers">animated stickers</a></td>
</tr>
<tr>
<td>is_video</td>
<td>Boolean</td>
<td><em>True</em>, if the sticker set contains <a href="https://telegram.org/blog/video-stickers-better-reactions">video stickers</a></td>
</tr>
<tr>
<td>contains_masks</td>
<td>Boolean</td>
<td><em>True</em>, if the sticker set contains masks</td>
</tr>
<tr>
<td>stickers</td>
<td>Array of <a href="#sticker">Sticker</a></td>
<td>List of all set stickers</td>
</tr>
<tr>
<td>thumb</td>
<td><a href="#photosize">PhotoSize</a></td>
<td><em>Optional</em>. Sticker set thumbnail in the .WEBP, .TGS, or .WEBM format</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="maskposition" href="#maskposition"><i class="anchor-icon"></i></a>MaskPosition</h4>
<p>This object describes the position on faces where a mask should be placed by default.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>point</td>
<td>String</td>
<td>The part of the face relative to which the mask should be placed. One of “forehead”, “eyes”, “mouth”, or “chin”.</td>
</tr>
<tr>
<td>x_shift</td>
<td>Float number</td>
<td>Shift by X-axis measured in widths of the mask scaled to the face size, from left to right. For example, choosing -1.0 will place mask just to the left of the default mask position.</td>
</tr>
<tr>
<td>y_shift</td>
<td>Float number</td>
<td>Shift by Y-axis measured in heights of the mask scaled to the face size, from top to bottom. For example, 1.0 will place the mask just below the default mask position.</td>
</tr>
<tr>
<td>scale</td>
<td>Float number</td>
<td>Mask scaling coefficient. For example, 2.0 means double size.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="sendsticker" href="#sendsticker"><i class="anchor-icon"></i></a>sendSticker</h4>
<p>Use this method to send static .WEBP, <a href="https://telegram.org/blog/animated-stickers">animated</a> .TGS, or <a href="https://telegram.org/blog/video-stickers-better-reactions">video</a> .WEBM stickers. On success, the sent <a href="#message">Message</a> is returned.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>sticker</td>
<td><a href="#inputfile">InputFile</a> or String</td>
<td>Yes</td>
<td>Sticker to send. Pass a file_id as String to send a file that exists on the Telegram servers (recommended), pass an HTTP URL as a String for Telegram to get a .WEBP file from the Internet, or upload a new one using multipart/form-data. <a href="#sending-files">More info on Sending Files »</a></td>
</tr>
<tr>
<td>disable_notification</td>
<td>Boolean</td>
<td>Optional</td>
<td>Sends the message <a href="https://telegram.org/blog/channels-2-0#silent-messages">silently</a>. Users will receive a notification with no sound.</td>
</tr>
<tr>
<td>protect_content</td>
<td>Boolean</td>
<td>Optional</td>
<td>Protects the contents of the sent message from forwarding and saving</td>
</tr>
<tr>
<td>reply_to_message_id</td>
<td>Integer</td>
<td>Optional</td>
<td>If the message is a reply, ID of the original message</td>
</tr>
<tr>
<td>allow_sending_without_reply</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the message should be sent even if the specified replied-to message is not found</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a> or <a href="#replykeyboardmarkup">ReplyKeyboardMarkup</a> or <a href="#replykeyboardremove">ReplyKeyboardRemove</a> or <a href="#forcereply">ForceReply</a></td>
<td>Optional</td>
<td>Additional interface options. A JSON-serialized object for an <a href="https://core.telegram.org/bots#inline-keyboards-and-on-the-fly-updating">inline keyboard</a>, <a href="https://core.telegram.org/bots#keyboards">custom reply keyboard</a>, instructions to remove reply keyboard or to force a reply from the user.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="getstickerset" href="#getstickerset"><i class="anchor-icon"></i></a>getStickerSet</h4>
<p>Use this method to get a sticker set. On success, a <a href="#stickerset">StickerSet</a> object is returned.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>name</td>
<td>String</td>
<td>Yes</td>
<td>Name of the sticker set</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="uploadstickerfile" href="#uploadstickerfile"><i class="anchor-icon"></i></a>uploadStickerFile</h4>
<p>Use this method to upload a .PNG file with a sticker for later use in <em>createNewStickerSet</em> and <em>addStickerToSet</em> methods (can be used multiple times). Returns the uploaded <a href="#file">File</a> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>user_id</td>
<td>Integer</td>
<td>Yes</td>
<td>User identifier of sticker file owner</td>
</tr>
<tr>
<td>png_sticker</td>
<td><a href="#inputfile">InputFile</a></td>
<td>Yes</td>
<td><strong>PNG</strong> image with the sticker, must be up to 512 kilobytes in size, dimensions must not exceed 512px, and either width or height must be exactly 512px. <a href="#sending-files">More info on Sending Files »</a></td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="createnewstickerset" href="#createnewstickerset"><i class="anchor-icon"></i></a>createNewStickerSet</h4>
<p>Use this method to create a new sticker set owned by a user. The bot will be able to edit the sticker set thus created. You <strong>must</strong> use exactly one of the fields <em>png_sticker</em>, <em>tgs_sticker</em>, or <em>webm_sticker</em>. Returns <em>True</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>user_id</td>
<td>Integer</td>
<td>Yes</td>
<td>User identifier of created sticker set owner</td>
</tr>
<tr>
<td>name</td>
<td>String</td>
<td>Yes</td>
<td>Short name of sticker set, to be used in <code>t.me/addstickers/</code> URLs (e.g., <em>animals</em>). Can contain only english letters, digits and underscores. Must begin with a letter, can&#39;t contain consecutive underscores and must end in <em>“_by_&lt;bot username&gt;”</em>. <em>&lt;bot_username&gt;</em> is case insensitive. 1-64 characters.</td>
</tr>
<tr>
<td>title</td>
<td>String</td>
<td>Yes</td>
<td>Sticker set title, 1-64 characters</td>
</tr>
<tr>
<td>png_sticker</td>
<td><a href="#inputfile">InputFile</a> or String</td>
<td>Optional</td>
<td><strong>PNG</strong> image with the sticker, must be up to 512 kilobytes in size, dimensions must not exceed 512px, and either width or height must be exactly 512px. Pass a <em>file_id</em> as a String to send a file that already exists on the Telegram servers, pass an HTTP URL as a String for Telegram to get a file from the Internet, or upload a new one using multipart/form-data. <a href="#sending-files">More info on Sending Files »</a></td>
</tr>
<tr>
<td>tgs_sticker</td>
<td><a href="#inputfile">InputFile</a></td>
<td>Optional</td>
<td><strong>TGS</strong> animation with the sticker, uploaded using multipart/form-data. See <a href="https://core.telegram.org/stickers#animated-sticker-requirements"><a href="https://core.telegram.org/stickers#animated-sticker-requirements">https://core.telegram.org/stickers#animated-sticker-requirements</a></a> for technical requirements</td>
</tr>
<tr>
<td>webm_sticker</td>
<td><a href="#inputfile">InputFile</a></td>
<td>Optional</td>
<td><strong>WEBM</strong> video with the sticker, uploaded using multipart/form-data. See <a href="https://core.telegram.org/stickers#video-sticker-requirements"><a href="https://core.telegram.org/stickers#video-sticker-requirements">https://core.telegram.org/stickers#video-sticker-requirements</a></a> for technical requirements</td>
</tr>
<tr>
<td>emojis</td>
<td>String</td>
<td>Yes</td>
<td>One or more emoji corresponding to the sticker</td>
</tr>
<tr>
<td>contains_masks</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if a set of mask stickers should be created</td>
</tr>
<tr>
<td>mask_position</td>
<td><a href="#maskposition">MaskPosition</a></td>
<td>Optional</td>
<td>A JSON-serialized object for position where the mask should be placed on faces</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="addstickertoset" href="#addstickertoset"><i class="anchor-icon"></i></a>addStickerToSet</h4>
<p>Use this method to add a new sticker to a set created by the bot. You <strong>must</strong> use exactly one of the fields <em>png_sticker</em>, <em>tgs_sticker</em>, or <em>webm_sticker</em>. Animated stickers can be added to animated sticker sets and only to them. Animated sticker sets can have up to 50 stickers. Static sticker sets can have up to 120 stickers. Returns <em>True</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>user_id</td>
<td>Integer</td>
<td>Yes</td>
<td>User identifier of sticker set owner</td>
</tr>
<tr>
<td>name</td>
<td>String</td>
<td>Yes</td>
<td>Sticker set name</td>
</tr>
<tr>
<td>png_sticker</td>
<td><a href="#inputfile">InputFile</a> or String</td>
<td>Optional</td>
<td><strong>PNG</strong> image with the sticker, must be up to 512 kilobytes in size, dimensions must not exceed 512px, and either width or height must be exactly 512px. Pass a <em>file_id</em> as a String to send a file that already exists on the Telegram servers, pass an HTTP URL as a String for Telegram to get a file from the Internet, or upload a new one using multipart/form-data. <a href="#sending-files">More info on Sending Files »</a></td>
</tr>
<tr>
<td>tgs_sticker</td>
<td><a href="#inputfile">InputFile</a></td>
<td>Optional</td>
<td><strong>TGS</strong> animation with the sticker, uploaded using multipart/form-data. See <a href="https://core.telegram.org/stickers#animated-sticker-requirements"><a href="https://core.telegram.org/stickers#animated-sticker-requirements">https://core.telegram.org/stickers#animated-sticker-requirements</a></a> for technical requirements</td>
</tr>
<tr>
<td>webm_sticker</td>
<td><a href="#inputfile">InputFile</a></td>
<td>Optional</td>
<td><strong>WEBM</strong> video with the sticker, uploaded using multipart/form-data. See <a href="https://core.telegram.org/stickers#video-sticker-requirements"><a href="https://core.telegram.org/stickers#video-sticker-requirements">https://core.telegram.org/stickers#video-sticker-requirements</a></a> for technical requirements</td>
</tr>
<tr>
<td>emojis</td>
<td>String</td>
<td>Yes</td>
<td>One or more emoji corresponding to the sticker</td>
</tr>
<tr>
<td>mask_position</td>
<td><a href="#maskposition">MaskPosition</a></td>
<td>Optional</td>
<td>A JSON-serialized object for position where the mask should be placed on faces</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="setstickerpositioninset" href="#setstickerpositioninset"><i class="anchor-icon"></i></a>setStickerPositionInSet</h4>
<p>Use this method to move a sticker in a set created by the bot to a specific position. Returns <em>True</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>sticker</td>
<td>String</td>
<td>Yes</td>
<td>File identifier of the sticker</td>
</tr>
<tr>
<td>position</td>
<td>Integer</td>
<td>Yes</td>
<td>New sticker position in the set, zero-based</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="deletestickerfromset" href="#deletestickerfromset"><i class="anchor-icon"></i></a>deleteStickerFromSet</h4>
<p>Use this method to delete a sticker from a set created by the bot. Returns <em>True</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>sticker</td>
<td>String</td>
<td>Yes</td>
<td>File identifier of the sticker</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="setstickersetthumb" href="#setstickersetthumb"><i class="anchor-icon"></i></a>setStickerSetThumb</h4>
<p>Use this method to set the thumbnail of a sticker set. Animated thumbnails can be set for animated sticker sets only. Video thumbnails can be set only for video sticker sets only. Returns <em>True</em> on success.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>name</td>
<td>String</td>
<td>Yes</td>
<td>Sticker set name</td>
</tr>
<tr>
<td>user_id</td>
<td>Integer</td>
<td>Yes</td>
<td>User identifier of the sticker set owner</td>
</tr>
<tr>
<td>thumb</td>
<td><a href="#inputfile">InputFile</a> or String</td>
<td>Optional</td>
<td>A <strong>PNG</strong> image with the thumbnail, must be up to 128 kilobytes in size and have width and height exactly 100px, or a <strong>TGS</strong> animation with the thumbnail up to 32 kilobytes in size; see <a href="https://core.telegram.org/stickers#animated-sticker-requirements"><a href="https://core.telegram.org/stickers#animated-sticker-requirements">https://core.telegram.org/stickers#animated-sticker-requirements</a></a> for animated sticker technical requirements, or a <strong>WEBM</strong> video with the thumbnail up to 32 kilobytes in size; see <a href="https://core.telegram.org/stickers#video-sticker-requirements"><a href="https://core.telegram.org/stickers#video-sticker-requirements">https://core.telegram.org/stickers#video-sticker-requirements</a></a> for video sticker technical requirements. Pass a <em>file_id</em> as a String to send a file that already exists on the Telegram servers, pass an HTTP URL as a String for Telegram to get a file from the Internet, or upload a new one using multipart/form-data. <a href="#sending-files">More info on Sending Files »</a>. Animated sticker set thumbnails can&#39;t be uploaded via HTTP URL.</td>
</tr>
</tbody>
</table>
<h3><a class="anchor" name="inline-mode" href="#inline-mode"><i class="anchor-icon"></i></a>Inline mode</h3>
<p>The following methods and objects allow your bot to work in <a href="/bots/inline">inline mode</a>.<br>Please see our <a href="/bots/inline">Introduction to Inline bots</a> for more details.</p>
<p>To enable this option, send the <code>/setinline</code> command to <a href="https://t.me/botfather">@BotFather</a> and provide the placeholder text that the user will see in the input field after typing your bot&#39;s name.</p>
<h4><a class="anchor" name="inlinequery" href="#inlinequery"><i class="anchor-icon"></i></a>InlineQuery</h4>
<p>This object represents an incoming inline query. When the user sends an empty query, your bot could return some default or trending results.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>id</td>
<td>String</td>
<td>Unique identifier for this query</td>
</tr>
<tr>
<td>from</td>
<td><a href="#user">User</a></td>
<td>Sender</td>
</tr>
<tr>
<td>query</td>
<td>String</td>
<td>Text of the query (up to 256 characters)</td>
</tr>
<tr>
<td>offset</td>
<td>String</td>
<td>Offset of the results to be returned, can be controlled by the bot</td>
</tr>
<tr>
<td>chat_type</td>
<td>String</td>
<td><em>Optional</em>. Type of the chat, from which the inline query was sent. Can be either “sender” for a private chat with the inline query sender, “private”, “group”, “supergroup”, or “channel”. The chat type should be always known for requests sent from official clients and most third-party clients, unless the request was sent from a secret chat</td>
</tr>
<tr>
<td>location</td>
<td><a href="#location">Location</a></td>
<td><em>Optional</em>. Sender location, only for bots that request user location</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="answerinlinequery" href="#answerinlinequery"><i class="anchor-icon"></i></a>answerInlineQuery</h4>
<p>Use this method to send answers to an inline query. On success, <em>True</em> is returned.<br>No more than <strong>50</strong> results per query are allowed.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>inline_query_id</td>
<td>String</td>
<td>Yes</td>
<td>Unique identifier for the answered query</td>
</tr>
<tr>
<td>results</td>
<td>Array of <a href="#inlinequeryresult">InlineQueryResult</a></td>
<td>Yes</td>
<td>A JSON-serialized array of results for the inline query</td>
</tr>
<tr>
<td>cache_time</td>
<td>Integer</td>
<td>Optional</td>
<td>The maximum amount of time in seconds that the result of the inline query may be cached on the server. Defaults to 300.</td>
</tr>
<tr>
<td>is_personal</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if results may be cached on the server side only for the user that sent the query. By default, results may be returned to any user who sends the same query</td>
</tr>
<tr>
<td>next_offset</td>
<td>String</td>
<td>Optional</td>
<td>Pass the offset that a client should send in the next query with the same text to receive more results. Pass an empty string if there are no more results or if you don&#39;t support pagination. Offset length can&#39;t exceed 64 bytes.</td>
</tr>
<tr>
<td>switch_pm_text</td>
<td>String</td>
<td>Optional</td>
<td>If passed, clients will display a button with specified text that switches the user to a private chat with the bot and sends the bot a start message with the parameter <em>switch_pm_parameter</em></td>
</tr>
<tr>
<td>switch_pm_parameter</td>
<td>String</td>
<td>Optional</td>
<td><a href="/bots#deep-linking">Deep-linking</a> parameter for the /start message sent to the bot when user presses the switch button. 1-64 characters, only <code>A-Z</code>, <code>a-z</code>, <code>0-9</code>, <code>_</code> and <code>-</code> are allowed.<br><br><em>Example:</em> An inline bot that sends YouTube videos can ask the user to connect the bot to their YouTube account to adapt search results accordingly. To do this, it displays a &#39;Connect your YouTube account&#39; button above the results, or even before showing any. The user presses the button, switches to a private chat with the bot and, in doing so, passes a start parameter that instructs the bot to return an OAuth link. Once done, the bot can offer a <a href="#inlinekeyboardmarkup"><em>switch_inline</em></a> button so that the user can easily return to the chat where they wanted to use the bot&#39;s inline capabilities.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="inlinequeryresult" href="#inlinequeryresult"><i class="anchor-icon"></i></a>InlineQueryResult</h4>
<p>This object represents one result of an inline query. Telegram clients currently support results of the following 20 types:</p>
<ul>
<li><a href="#inlinequeryresultcachedaudio">InlineQueryResultCachedAudio</a></li>
<li><a href="#inlinequeryresultcacheddocument">InlineQueryResultCachedDocument</a></li>
<li><a href="#inlinequeryresultcachedgif">InlineQueryResultCachedGif</a></li>
<li><a href="#inlinequeryresultcachedmpeg4gif">InlineQueryResultCachedMpeg4Gif</a></li>
<li><a href="#inlinequeryresultcachedphoto">InlineQueryResultCachedPhoto</a></li>
<li><a href="#inlinequeryresultcachedsticker">InlineQueryResultCachedSticker</a></li>
<li><a href="#inlinequeryresultcachedvideo">InlineQueryResultCachedVideo</a></li>
<li><a href="#inlinequeryresultcachedvoice">InlineQueryResultCachedVoice</a></li>
<li><a href="#inlinequeryresultarticle">InlineQueryResultArticle</a></li>
<li><a href="#inlinequeryresultaudio">InlineQueryResultAudio</a></li>
<li><a href="#inlinequeryresultcontact">InlineQueryResultContact</a></li>
<li><a href="#inlinequeryresultgame">InlineQueryResultGame</a></li>
<li><a href="#inlinequeryresultdocument">InlineQueryResultDocument</a></li>
<li><a href="#inlinequeryresultgif">InlineQueryResultGif</a></li>
<li><a href="#inlinequeryresultlocation">InlineQueryResultLocation</a></li>
<li><a href="#inlinequeryresultmpeg4gif">InlineQueryResultMpeg4Gif</a></li>
<li><a href="#inlinequeryresultphoto">InlineQueryResultPhoto</a></li>
<li><a href="#inlinequeryresultvenue">InlineQueryResultVenue</a></li>
<li><a href="#inlinequeryresultvideo">InlineQueryResultVideo</a></li>
<li><a href="#inlinequeryresultvoice">InlineQueryResultVoice</a></li>
</ul>
<p><strong>Note:</strong> All URLs passed in inline query results will be available to end users and therefore must be assumed to be <strong>public</strong>.</p>
<h4><a class="anchor" name="inlinequeryresultarticle" href="#inlinequeryresultarticle"><i class="anchor-icon"></i></a>InlineQueryResultArticle</h4>
<p>Represents a link to an article or web page.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Type of the result, must be <em>article</em></td>
</tr>
<tr>
<td>id</td>
<td>String</td>
<td>Unique identifier for this result, 1-64 Bytes</td>
</tr>
<tr>
<td>title</td>
<td>String</td>
<td>Title of the result</td>
</tr>
<tr>
<td>input_message_content</td>
<td><a href="#inputmessagecontent">InputMessageContent</a></td>
<td>Content of the message to be sent</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a></td>
<td><em>Optional</em>. <a href="/bots#inline-keyboards-and-on-the-fly-updating">Inline keyboard</a> attached to the message</td>
</tr>
<tr>
<td>url</td>
<td>String</td>
<td><em>Optional</em>. URL of the result</td>
</tr>
<tr>
<td>hide_url</td>
<td>Boolean</td>
<td><em>Optional</em>. Pass <em>True</em>, if you don&#39;t want the URL to be shown in the message</td>
</tr>
<tr>
<td>description</td>
<td>String</td>
<td><em>Optional</em>. Short description of the result</td>
</tr>
<tr>
<td>thumb_url</td>
<td>String</td>
<td><em>Optional</em>. Url of the thumbnail for the result</td>
</tr>
<tr>
<td>thumb_width</td>
<td>Integer</td>
<td><em>Optional</em>. Thumbnail width</td>
</tr>
<tr>
<td>thumb_height</td>
<td>Integer</td>
<td><em>Optional</em>. Thumbnail height</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="inlinequeryresultphoto" href="#inlinequeryresultphoto"><i class="anchor-icon"></i></a>InlineQueryResultPhoto</h4>
<p>Represents a link to a photo. By default, this photo will be sent by the user with optional caption. Alternatively, you can use <em>input_message_content</em> to send a message with the specified content instead of the photo.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Type of the result, must be <em>photo</em></td>
</tr>
<tr>
<td>id</td>
<td>String</td>
<td>Unique identifier for this result, 1-64 bytes</td>
</tr>
<tr>
<td>photo_url</td>
<td>String</td>
<td>A valid URL of the photo. Photo must be in <strong>JPEG</strong> format. Photo size must not exceed 5MB</td>
</tr>
<tr>
<td>thumb_url</td>
<td>String</td>
<td>URL of the thumbnail for the photo</td>
</tr>
<tr>
<td>photo_width</td>
<td>Integer</td>
<td><em>Optional</em>. Width of the photo</td>
</tr>
<tr>
<td>photo_height</td>
<td>Integer</td>
<td><em>Optional</em>. Height of the photo</td>
</tr>
<tr>
<td>title</td>
<td>String</td>
<td><em>Optional</em>. Title for the result</td>
</tr>
<tr>
<td>description</td>
<td>String</td>
<td><em>Optional</em>. Short description of the result</td>
</tr>
<tr>
<td>caption</td>
<td>String</td>
<td><em>Optional</em>. Caption of the photo to be sent, 0-1024 characters after entities parsing</td>
</tr>
<tr>
<td>parse_mode</td>
<td>String</td>
<td><em>Optional</em>. Mode for parsing entities in the photo caption. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>caption_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td><em>Optional</em>. List of special entities that appear in the caption, which can be specified instead of <em>parse_mode</em></td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a></td>
<td><em>Optional</em>. <a href="/bots#inline-keyboards-and-on-the-fly-updating">Inline keyboard</a> attached to the message</td>
</tr>
<tr>
<td>input_message_content</td>
<td><a href="#inputmessagecontent">InputMessageContent</a></td>
<td><em>Optional</em>. Content of the message to be sent instead of the photo</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="inlinequeryresultgif" href="#inlinequeryresultgif"><i class="anchor-icon"></i></a>InlineQueryResultGif</h4>
<p>Represents a link to an animated GIF file. By default, this animated GIF file will be sent by the user with optional caption. Alternatively, you can use <em>input_message_content</em> to send a message with the specified content instead of the animation.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Type of the result, must be <em>gif</em></td>
</tr>
<tr>
<td>id</td>
<td>String</td>
<td>Unique identifier for this result, 1-64 bytes</td>
</tr>
<tr>
<td>gif_url</td>
<td>String</td>
<td>A valid URL for the GIF file. File size must not exceed 1MB</td>
</tr>
<tr>
<td>gif_width</td>
<td>Integer</td>
<td><em>Optional</em>. Width of the GIF</td>
</tr>
<tr>
<td>gif_height</td>
<td>Integer</td>
<td><em>Optional</em>. Height of the GIF</td>
</tr>
<tr>
<td>gif_duration</td>
<td>Integer</td>
<td><em>Optional</em>. Duration of the GIF in seconds</td>
</tr>
<tr>
<td>thumb_url</td>
<td>String</td>
<td>URL of the static (JPEG or GIF) or animated (MPEG4) thumbnail for the result</td>
</tr>
<tr>
<td>thumb_mime_type</td>
<td>String</td>
<td><em>Optional</em>. MIME type of the thumbnail, must be one of “image/jpeg”, “image/gif”, or “video/mp4”. Defaults to “image/jpeg”</td>
</tr>
<tr>
<td>title</td>
<td>String</td>
<td><em>Optional</em>. Title for the result</td>
</tr>
<tr>
<td>caption</td>
<td>String</td>
<td><em>Optional</em>. Caption of the GIF file to be sent, 0-1024 characters after entities parsing</td>
</tr>
<tr>
<td>parse_mode</td>
<td>String</td>
<td><em>Optional</em>. Mode for parsing entities in the caption. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>caption_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td><em>Optional</em>. List of special entities that appear in the caption, which can be specified instead of <em>parse_mode</em></td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a></td>
<td><em>Optional</em>. <a href="/bots#inline-keyboards-and-on-the-fly-updating">Inline keyboard</a> attached to the message</td>
</tr>
<tr>
<td>input_message_content</td>
<td><a href="#inputmessagecontent">InputMessageContent</a></td>
<td><em>Optional</em>. Content of the message to be sent instead of the GIF animation</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="inlinequeryresultmpeg4gif" href="#inlinequeryresultmpeg4gif"><i class="anchor-icon"></i></a>InlineQueryResultMpeg4Gif</h4>
<p>Represents a link to a video animation (H.264/MPEG-4 AVC video without sound). By default, this animated MPEG-4 file will be sent by the user with optional caption. Alternatively, you can use <em>input_message_content</em> to send a message with the specified content instead of the animation.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Type of the result, must be <em>mpeg4_gif</em></td>
</tr>
<tr>
<td>id</td>
<td>String</td>
<td>Unique identifier for this result, 1-64 bytes</td>
</tr>
<tr>
<td>mpeg4_url</td>
<td>String</td>
<td>A valid URL for the MP4 file. File size must not exceed 1MB</td>
</tr>
<tr>
<td>mpeg4_width</td>
<td>Integer</td>
<td><em>Optional</em>. Video width</td>
</tr>
<tr>
<td>mpeg4_height</td>
<td>Integer</td>
<td><em>Optional</em>. Video height</td>
</tr>
<tr>
<td>mpeg4_duration</td>
<td>Integer</td>
<td><em>Optional</em>. Video duration in seconds</td>
</tr>
<tr>
<td>thumb_url</td>
<td>String</td>
<td>URL of the static (JPEG or GIF) or animated (MPEG4) thumbnail for the result</td>
</tr>
<tr>
<td>thumb_mime_type</td>
<td>String</td>
<td><em>Optional</em>. MIME type of the thumbnail, must be one of “image/jpeg”, “image/gif”, or “video/mp4”. Defaults to “image/jpeg”</td>
</tr>
<tr>
<td>title</td>
<td>String</td>
<td><em>Optional</em>. Title for the result</td>
</tr>
<tr>
<td>caption</td>
<td>String</td>
<td><em>Optional</em>. Caption of the MPEG-4 file to be sent, 0-1024 characters after entities parsing</td>
</tr>
<tr>
<td>parse_mode</td>
<td>String</td>
<td><em>Optional</em>. Mode for parsing entities in the caption. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>caption_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td><em>Optional</em>. List of special entities that appear in the caption, which can be specified instead of <em>parse_mode</em></td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a></td>
<td><em>Optional</em>. <a href="/bots#inline-keyboards-and-on-the-fly-updating">Inline keyboard</a> attached to the message</td>
</tr>
<tr>
<td>input_message_content</td>
<td><a href="#inputmessagecontent">InputMessageContent</a></td>
<td><em>Optional</em>. Content of the message to be sent instead of the video animation</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="inlinequeryresultvideo" href="#inlinequeryresultvideo"><i class="anchor-icon"></i></a>InlineQueryResultVideo</h4>
<p>Represents a link to a page containing an embedded video player or a video file. By default, this video file will be sent by the user with an optional caption. Alternatively, you can use <em>input_message_content</em> to send a message with the specified content instead of the video.</p>
<blockquote>
<p>If an InlineQueryResultVideo message contains an embedded video (e.g., YouTube), you <strong>must</strong> replace its content using <em>input_message_content</em>.</p>
</blockquote>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Type of the result, must be <em>video</em></td>
</tr>
<tr>
<td>id</td>
<td>String</td>
<td>Unique identifier for this result, 1-64 bytes</td>
</tr>
<tr>
<td>video_url</td>
<td>String</td>
<td>A valid URL for the embedded video player or video file</td>
</tr>
<tr>
<td>mime_type</td>
<td>String</td>
<td>Mime type of the content of video url, “text/html” or “video/mp4”</td>
</tr>
<tr>
<td>thumb_url</td>
<td>String</td>
<td>URL of the thumbnail (JPEG only) for the video</td>
</tr>
<tr>
<td>title</td>
<td>String</td>
<td>Title for the result</td>
</tr>
<tr>
<td>caption</td>
<td>String</td>
<td><em>Optional</em>. Caption of the video to be sent, 0-1024 characters after entities parsing</td>
</tr>
<tr>
<td>parse_mode</td>
<td>String</td>
<td><em>Optional</em>. Mode for parsing entities in the video caption. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>caption_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td><em>Optional</em>. List of special entities that appear in the caption, which can be specified instead of <em>parse_mode</em></td>
</tr>
<tr>
<td>video_width</td>
<td>Integer</td>
<td><em>Optional</em>. Video width</td>
</tr>
<tr>
<td>video_height</td>
<td>Integer</td>
<td><em>Optional</em>. Video height</td>
</tr>
<tr>
<td>video_duration</td>
<td>Integer</td>
<td><em>Optional</em>. Video duration in seconds</td>
</tr>
<tr>
<td>description</td>
<td>String</td>
<td><em>Optional</em>. Short description of the result</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a></td>
<td><em>Optional</em>. <a href="/bots#inline-keyboards-and-on-the-fly-updating">Inline keyboard</a> attached to the message</td>
</tr>
<tr>
<td>input_message_content</td>
<td><a href="#inputmessagecontent">InputMessageContent</a></td>
<td><em>Optional</em>. Content of the message to be sent instead of the video. This field is <strong>required</strong> if InlineQueryResultVideo is used to send an HTML-page as a result (e.g., a YouTube video).</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="inlinequeryresultaudio" href="#inlinequeryresultaudio"><i class="anchor-icon"></i></a>InlineQueryResultAudio</h4>
<p>Represents a link to an MP3 audio file. By default, this audio file will be sent by the user. Alternatively, you can use <em>input_message_content</em> to send a message with the specified content instead of the audio.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Type of the result, must be <em>audio</em></td>
</tr>
<tr>
<td>id</td>
<td>String</td>
<td>Unique identifier for this result, 1-64 bytes</td>
</tr>
<tr>
<td>audio_url</td>
<td>String</td>
<td>A valid URL for the audio file</td>
</tr>
<tr>
<td>title</td>
<td>String</td>
<td>Title</td>
</tr>
<tr>
<td>caption</td>
<td>String</td>
<td><em>Optional</em>. Caption, 0-1024 characters after entities parsing</td>
</tr>
<tr>
<td>parse_mode</td>
<td>String</td>
<td><em>Optional</em>. Mode for parsing entities in the audio caption. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>caption_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td><em>Optional</em>. List of special entities that appear in the caption, which can be specified instead of <em>parse_mode</em></td>
</tr>
<tr>
<td>performer</td>
<td>String</td>
<td><em>Optional</em>. Performer</td>
</tr>
<tr>
<td>audio_duration</td>
<td>Integer</td>
<td><em>Optional</em>. Audio duration in seconds</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a></td>
<td><em>Optional</em>. <a href="/bots#inline-keyboards-and-on-the-fly-updating">Inline keyboard</a> attached to the message</td>
</tr>
<tr>
<td>input_message_content</td>
<td><a href="#inputmessagecontent">InputMessageContent</a></td>
<td><em>Optional</em>. Content of the message to be sent instead of the audio</td>
</tr>
</tbody>
</table>
<p><strong>Note:</strong> This will only work in Telegram versions released after 9 April, 2016. Older clients will ignore them.</p>
<h4><a class="anchor" name="inlinequeryresultvoice" href="#inlinequeryresultvoice"><i class="anchor-icon"></i></a>InlineQueryResultVoice</h4>
<p>Represents a link to a voice recording in an .OGG container encoded with OPUS. By default, this voice recording will be sent by the user. Alternatively, you can use <em>input_message_content</em> to send a message with the specified content instead of the the voice message.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Type of the result, must be <em>voice</em></td>
</tr>
<tr>
<td>id</td>
<td>String</td>
<td>Unique identifier for this result, 1-64 bytes</td>
</tr>
<tr>
<td>voice_url</td>
<td>String</td>
<td>A valid URL for the voice recording</td>
</tr>
<tr>
<td>title</td>
<td>String</td>
<td>Recording title</td>
</tr>
<tr>
<td>caption</td>
<td>String</td>
<td><em>Optional</em>. Caption, 0-1024 characters after entities parsing</td>
</tr>
<tr>
<td>parse_mode</td>
<td>String</td>
<td><em>Optional</em>. Mode for parsing entities in the voice message caption. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>caption_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td><em>Optional</em>. List of special entities that appear in the caption, which can be specified instead of <em>parse_mode</em></td>
</tr>
<tr>
<td>voice_duration</td>
<td>Integer</td>
<td><em>Optional</em>. Recording duration in seconds</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a></td>
<td><em>Optional</em>. <a href="/bots#inline-keyboards-and-on-the-fly-updating">Inline keyboard</a> attached to the message</td>
</tr>
<tr>
<td>input_message_content</td>
<td><a href="#inputmessagecontent">InputMessageContent</a></td>
<td><em>Optional</em>. Content of the message to be sent instead of the voice recording</td>
</tr>
</tbody>
</table>
<p><strong>Note:</strong> This will only work in Telegram versions released after 9 April, 2016. Older clients will ignore them.</p>
<h4><a class="anchor" name="inlinequeryresultdocument" href="#inlinequeryresultdocument"><i class="anchor-icon"></i></a>InlineQueryResultDocument</h4>
<p>Represents a link to a file. By default, this file will be sent by the user with an optional caption. Alternatively, you can use <em>input_message_content</em> to send a message with the specified content instead of the file. Currently, only <strong>.PDF</strong> and <strong>.ZIP</strong> files can be sent using this method.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Type of the result, must be <em>document</em></td>
</tr>
<tr>
<td>id</td>
<td>String</td>
<td>Unique identifier for this result, 1-64 bytes</td>
</tr>
<tr>
<td>title</td>
<td>String</td>
<td>Title for the result</td>
</tr>
<tr>
<td>caption</td>
<td>String</td>
<td><em>Optional</em>. Caption of the document to be sent, 0-1024 characters after entities parsing</td>
</tr>
<tr>
<td>parse_mode</td>
<td>String</td>
<td><em>Optional</em>. Mode for parsing entities in the document caption. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>caption_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td><em>Optional</em>. List of special entities that appear in the caption, which can be specified instead of <em>parse_mode</em></td>
</tr>
<tr>
<td>document_url</td>
<td>String</td>
<td>A valid URL for the file</td>
</tr>
<tr>
<td>mime_type</td>
<td>String</td>
<td>Mime type of the content of the file, either “application/pdf” or “application/zip”</td>
</tr>
<tr>
<td>description</td>
<td>String</td>
<td><em>Optional</em>. Short description of the result</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a></td>
<td><em>Optional</em>. Inline keyboard attached to the message</td>
</tr>
<tr>
<td>input_message_content</td>
<td><a href="#inputmessagecontent">InputMessageContent</a></td>
<td><em>Optional</em>. Content of the message to be sent instead of the file</td>
</tr>
<tr>
<td>thumb_url</td>
<td>String</td>
<td><em>Optional</em>. URL of the thumbnail (JPEG only) for the file</td>
</tr>
<tr>
<td>thumb_width</td>
<td>Integer</td>
<td><em>Optional</em>. Thumbnail width</td>
</tr>
<tr>
<td>thumb_height</td>
<td>Integer</td>
<td><em>Optional</em>. Thumbnail height</td>
</tr>
</tbody>
</table>
<p><strong>Note:</strong> This will only work in Telegram versions released after 9 April, 2016. Older clients will ignore them.</p>
<h4><a class="anchor" name="inlinequeryresultlocation" href="#inlinequeryresultlocation"><i class="anchor-icon"></i></a>InlineQueryResultLocation</h4>
<p>Represents a location on a map. By default, the location will be sent by the user. Alternatively, you can use <em>input_message_content</em> to send a message with the specified content instead of the location.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Type of the result, must be <em>location</em></td>
</tr>
<tr>
<td>id</td>
<td>String</td>
<td>Unique identifier for this result, 1-64 Bytes</td>
</tr>
<tr>
<td>latitude</td>
<td>Float number</td>
<td>Location latitude in degrees</td>
</tr>
<tr>
<td>longitude</td>
<td>Float number</td>
<td>Location longitude in degrees</td>
</tr>
<tr>
<td>title</td>
<td>String</td>
<td>Location title</td>
</tr>
<tr>
<td>horizontal_accuracy</td>
<td>Float number</td>
<td><em>Optional</em>. The radius of uncertainty for the location, measured in meters; 0-1500</td>
</tr>
<tr>
<td>live_period</td>
<td>Integer</td>
<td><em>Optional</em>. Period in seconds for which the location can be updated, should be between 60 and 86400.</td>
</tr>
<tr>
<td>heading</td>
<td>Integer</td>
<td><em>Optional</em>. For live locations, a direction in which the user is moving, in degrees. Must be between 1 and 360 if specified.</td>
</tr>
<tr>
<td>proximity_alert_radius</td>
<td>Integer</td>
<td><em>Optional</em>. For live locations, a maximum distance for proximity alerts about approaching another chat member, in meters. Must be between 1 and 100000 if specified.</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a></td>
<td><em>Optional</em>. <a href="/bots#inline-keyboards-and-on-the-fly-updating">Inline keyboard</a> attached to the message</td>
</tr>
<tr>
<td>input_message_content</td>
<td><a href="#inputmessagecontent">InputMessageContent</a></td>
<td><em>Optional</em>. Content of the message to be sent instead of the location</td>
</tr>
<tr>
<td>thumb_url</td>
<td>String</td>
<td><em>Optional</em>. Url of the thumbnail for the result</td>
</tr>
<tr>
<td>thumb_width</td>
<td>Integer</td>
<td><em>Optional</em>. Thumbnail width</td>
</tr>
<tr>
<td>thumb_height</td>
<td>Integer</td>
<td><em>Optional</em>. Thumbnail height</td>
</tr>
</tbody>
</table>
<p><strong>Note:</strong> This will only work in Telegram versions released after 9 April, 2016. Older clients will ignore them.</p>
<h4><a class="anchor" name="inlinequeryresultvenue" href="#inlinequeryresultvenue"><i class="anchor-icon"></i></a>InlineQueryResultVenue</h4>
<p>Represents a venue. By default, the venue will be sent by the user. Alternatively, you can use <em>input_message_content</em> to send a message with the specified content instead of the venue.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Type of the result, must be <em>venue</em></td>
</tr>
<tr>
<td>id</td>
<td>String</td>
<td>Unique identifier for this result, 1-64 Bytes</td>
</tr>
<tr>
<td>latitude</td>
<td>Float</td>
<td>Latitude of the venue location in degrees</td>
</tr>
<tr>
<td>longitude</td>
<td>Float</td>
<td>Longitude of the venue location in degrees</td>
</tr>
<tr>
<td>title</td>
<td>String</td>
<td>Title of the venue</td>
</tr>
<tr>
<td>address</td>
<td>String</td>
<td>Address of the venue</td>
</tr>
<tr>
<td>foursquare_id</td>
<td>String</td>
<td><em>Optional</em>. Foursquare identifier of the venue if known</td>
</tr>
<tr>
<td>foursquare_type</td>
<td>String</td>
<td><em>Optional</em>. Foursquare type of the venue, if known. (For example, “arts_entertainment/default”, “arts_entertainment/aquarium” or “food/icecream”.)</td>
</tr>
<tr>
<td>google_place_id</td>
<td>String</td>
<td><em>Optional</em>. Google Places identifier of the venue</td>
</tr>
<tr>
<td>google_place_type</td>
<td>String</td>
<td><em>Optional</em>. Google Places type of the venue. (See <a href="https://developers.google.com/places/web-service/supported_types">supported types</a>.)</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a></td>
<td><em>Optional</em>. <a href="/bots#inline-keyboards-and-on-the-fly-updating">Inline keyboard</a> attached to the message</td>
</tr>
<tr>
<td>input_message_content</td>
<td><a href="#inputmessagecontent">InputMessageContent</a></td>
<td><em>Optional</em>. Content of the message to be sent instead of the venue</td>
</tr>
<tr>
<td>thumb_url</td>
<td>String</td>
<td><em>Optional</em>. Url of the thumbnail for the result</td>
</tr>
<tr>
<td>thumb_width</td>
<td>Integer</td>
<td><em>Optional</em>. Thumbnail width</td>
</tr>
<tr>
<td>thumb_height</td>
<td>Integer</td>
<td><em>Optional</em>. Thumbnail height</td>
</tr>
</tbody>
</table>
<p><strong>Note:</strong> This will only work in Telegram versions released after 9 April, 2016. Older clients will ignore them.</p>
<h4><a class="anchor" name="inlinequeryresultcontact" href="#inlinequeryresultcontact"><i class="anchor-icon"></i></a>InlineQueryResultContact</h4>
<p>Represents a contact with a phone number. By default, this contact will be sent by the user. Alternatively, you can use <em>input_message_content</em> to send a message with the specified content instead of the contact.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Type of the result, must be <em>contact</em></td>
</tr>
<tr>
<td>id</td>
<td>String</td>
<td>Unique identifier for this result, 1-64 Bytes</td>
</tr>
<tr>
<td>phone_number</td>
<td>String</td>
<td>Contact&#39;s phone number</td>
</tr>
<tr>
<td>first_name</td>
<td>String</td>
<td>Contact&#39;s first name</td>
</tr>
<tr>
<td>last_name</td>
<td>String</td>
<td><em>Optional</em>. Contact&#39;s last name</td>
</tr>
<tr>
<td>vcard</td>
<td>String</td>
<td><em>Optional</em>. Additional data about the contact in the form of a <a href="https://en.wikipedia.org/wiki/VCard">vCard</a>, 0-2048 bytes</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a></td>
<td><em>Optional</em>. <a href="/bots#inline-keyboards-and-on-the-fly-updating">Inline keyboard</a> attached to the message</td>
</tr>
<tr>
<td>input_message_content</td>
<td><a href="#inputmessagecontent">InputMessageContent</a></td>
<td><em>Optional</em>. Content of the message to be sent instead of the contact</td>
</tr>
<tr>
<td>thumb_url</td>
<td>String</td>
<td><em>Optional</em>. Url of the thumbnail for the result</td>
</tr>
<tr>
<td>thumb_width</td>
<td>Integer</td>
<td><em>Optional</em>. Thumbnail width</td>
</tr>
<tr>
<td>thumb_height</td>
<td>Integer</td>
<td><em>Optional</em>. Thumbnail height</td>
</tr>
</tbody>
</table>
<p><strong>Note:</strong> This will only work in Telegram versions released after 9 April, 2016. Older clients will ignore them.</p>
<h4><a class="anchor" name="inlinequeryresultgame" href="#inlinequeryresultgame"><i class="anchor-icon"></i></a>InlineQueryResultGame</h4>
<p>Represents a <a href="#games">Game</a>.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Type of the result, must be <em>game</em></td>
</tr>
<tr>
<td>id</td>
<td>String</td>
<td>Unique identifier for this result, 1-64 bytes</td>
</tr>
<tr>
<td>game_short_name</td>
<td>String</td>
<td>Short name of the game</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a></td>
<td><em>Optional</em>. <a href="/bots#inline-keyboards-and-on-the-fly-updating">Inline keyboard</a> attached to the message</td>
</tr>
</tbody>
</table>
<p><strong>Note:</strong> This will only work in Telegram versions released after October 1, 2016. Older clients will not display any inline results if a game result is among them.</p>
<h4><a class="anchor" name="inlinequeryresultcachedphoto" href="#inlinequeryresultcachedphoto"><i class="anchor-icon"></i></a>InlineQueryResultCachedPhoto</h4>
<p>Represents a link to a photo stored on the Telegram servers. By default, this photo will be sent by the user with an optional caption. Alternatively, you can use <em>input_message_content</em> to send a message with the specified content instead of the photo.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Type of the result, must be <em>photo</em></td>
</tr>
<tr>
<td>id</td>
<td>String</td>
<td>Unique identifier for this result, 1-64 bytes</td>
</tr>
<tr>
<td>photo_file_id</td>
<td>String</td>
<td>A valid file identifier of the photo</td>
</tr>
<tr>
<td>title</td>
<td>String</td>
<td><em>Optional</em>. Title for the result</td>
</tr>
<tr>
<td>description</td>
<td>String</td>
<td><em>Optional</em>. Short description of the result</td>
</tr>
<tr>
<td>caption</td>
<td>String</td>
<td><em>Optional</em>. Caption of the photo to be sent, 0-1024 characters after entities parsing</td>
</tr>
<tr>
<td>parse_mode</td>
<td>String</td>
<td><em>Optional</em>. Mode for parsing entities in the photo caption. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>caption_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td><em>Optional</em>. List of special entities that appear in the caption, which can be specified instead of <em>parse_mode</em></td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a></td>
<td><em>Optional</em>. <a href="/bots#inline-keyboards-and-on-the-fly-updating">Inline keyboard</a> attached to the message</td>
</tr>
<tr>
<td>input_message_content</td>
<td><a href="#inputmessagecontent">InputMessageContent</a></td>
<td><em>Optional</em>. Content of the message to be sent instead of the photo</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="inlinequeryresultcachedgif" href="#inlinequeryresultcachedgif"><i class="anchor-icon"></i></a>InlineQueryResultCachedGif</h4>
<p>Represents a link to an animated GIF file stored on the Telegram servers. By default, this animated GIF file will be sent by the user with an optional caption. Alternatively, you can use <em>input_message_content</em> to send a message with specified content instead of the animation.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Type of the result, must be <em>gif</em></td>
</tr>
<tr>
<td>id</td>
<td>String</td>
<td>Unique identifier for this result, 1-64 bytes</td>
</tr>
<tr>
<td>gif_file_id</td>
<td>String</td>
<td>A valid file identifier for the GIF file</td>
</tr>
<tr>
<td>title</td>
<td>String</td>
<td><em>Optional</em>. Title for the result</td>
</tr>
<tr>
<td>caption</td>
<td>String</td>
<td><em>Optional</em>. Caption of the GIF file to be sent, 0-1024 characters after entities parsing</td>
</tr>
<tr>
<td>parse_mode</td>
<td>String</td>
<td><em>Optional</em>. Mode for parsing entities in the caption. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>caption_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td><em>Optional</em>. List of special entities that appear in the caption, which can be specified instead of <em>parse_mode</em></td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a></td>
<td><em>Optional</em>. <a href="/bots#inline-keyboards-and-on-the-fly-updating">Inline keyboard</a> attached to the message</td>
</tr>
<tr>
<td>input_message_content</td>
<td><a href="#inputmessagecontent">InputMessageContent</a></td>
<td><em>Optional</em>. Content of the message to be sent instead of the GIF animation</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="inlinequeryresultcachedmpeg4gif" href="#inlinequeryresultcachedmpeg4gif"><i class="anchor-icon"></i></a>InlineQueryResultCachedMpeg4Gif</h4>
<p>Represents a link to a video animation (H.264/MPEG-4 AVC video without sound) stored on the Telegram servers. By default, this animated MPEG-4 file will be sent by the user with an optional caption. Alternatively, you can use <em>input_message_content</em> to send a message with the specified content instead of the animation.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Type of the result, must be <em>mpeg4_gif</em></td>
</tr>
<tr>
<td>id</td>
<td>String</td>
<td>Unique identifier for this result, 1-64 bytes</td>
</tr>
<tr>
<td>mpeg4_file_id</td>
<td>String</td>
<td>A valid file identifier for the MP4 file</td>
</tr>
<tr>
<td>title</td>
<td>String</td>
<td><em>Optional</em>. Title for the result</td>
</tr>
<tr>
<td>caption</td>
<td>String</td>
<td><em>Optional</em>. Caption of the MPEG-4 file to be sent, 0-1024 characters after entities parsing</td>
</tr>
<tr>
<td>parse_mode</td>
<td>String</td>
<td><em>Optional</em>. Mode for parsing entities in the caption. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>caption_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td><em>Optional</em>. List of special entities that appear in the caption, which can be specified instead of <em>parse_mode</em></td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a></td>
<td><em>Optional</em>. <a href="/bots#inline-keyboards-and-on-the-fly-updating">Inline keyboard</a> attached to the message</td>
</tr>
<tr>
<td>input_message_content</td>
<td><a href="#inputmessagecontent">InputMessageContent</a></td>
<td><em>Optional</em>. Content of the message to be sent instead of the video animation</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="inlinequeryresultcachedsticker" href="#inlinequeryresultcachedsticker"><i class="anchor-icon"></i></a>InlineQueryResultCachedSticker</h4>
<p>Represents a link to a sticker stored on the Telegram servers. By default, this sticker will be sent by the user. Alternatively, you can use <em>input_message_content</em> to send a message with the specified content instead of the sticker.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Type of the result, must be <em>sticker</em></td>
</tr>
<tr>
<td>id</td>
<td>String</td>
<td>Unique identifier for this result, 1-64 bytes</td>
</tr>
<tr>
<td>sticker_file_id</td>
<td>String</td>
<td>A valid file identifier of the sticker</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a></td>
<td><em>Optional</em>. <a href="/bots#inline-keyboards-and-on-the-fly-updating">Inline keyboard</a> attached to the message</td>
</tr>
<tr>
<td>input_message_content</td>
<td><a href="#inputmessagecontent">InputMessageContent</a></td>
<td><em>Optional</em>. Content of the message to be sent instead of the sticker</td>
</tr>
</tbody>
</table>
<p><strong>Note:</strong> This will only work in Telegram versions released after 9 April, 2016 for static stickers and after 06 July, 2019 for <a href="https://telegram.org/blog/animated-stickers">animated stickers</a>. Older clients will ignore them.</p>
<h4><a class="anchor" name="inlinequeryresultcacheddocument" href="#inlinequeryresultcacheddocument"><i class="anchor-icon"></i></a>InlineQueryResultCachedDocument</h4>
<p>Represents a link to a file stored on the Telegram servers. By default, this file will be sent by the user with an optional caption. Alternatively, you can use <em>input_message_content</em> to send a message with the specified content instead of the file.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Type of the result, must be <em>document</em></td>
</tr>
<tr>
<td>id</td>
<td>String</td>
<td>Unique identifier for this result, 1-64 bytes</td>
</tr>
<tr>
<td>title</td>
<td>String</td>
<td>Title for the result</td>
</tr>
<tr>
<td>document_file_id</td>
<td>String</td>
<td>A valid file identifier for the file</td>
</tr>
<tr>
<td>description</td>
<td>String</td>
<td><em>Optional</em>. Short description of the result</td>
</tr>
<tr>
<td>caption</td>
<td>String</td>
<td><em>Optional</em>. Caption of the document to be sent, 0-1024 characters after entities parsing</td>
</tr>
<tr>
<td>parse_mode</td>
<td>String</td>
<td><em>Optional</em>. Mode for parsing entities in the document caption. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>caption_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td><em>Optional</em>. List of special entities that appear in the caption, which can be specified instead of <em>parse_mode</em></td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a></td>
<td><em>Optional</em>. <a href="/bots#inline-keyboards-and-on-the-fly-updating">Inline keyboard</a> attached to the message</td>
</tr>
<tr>
<td>input_message_content</td>
<td><a href="#inputmessagecontent">InputMessageContent</a></td>
<td><em>Optional</em>. Content of the message to be sent instead of the file</td>
</tr>
</tbody>
</table>
<p><strong>Note:</strong> This will only work in Telegram versions released after 9 April, 2016. Older clients will ignore them.</p>
<h4><a class="anchor" name="inlinequeryresultcachedvideo" href="#inlinequeryresultcachedvideo"><i class="anchor-icon"></i></a>InlineQueryResultCachedVideo</h4>
<p>Represents a link to a video file stored on the Telegram servers. By default, this video file will be sent by the user with an optional caption. Alternatively, you can use <em>input_message_content</em> to send a message with the specified content instead of the video.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Type of the result, must be <em>video</em></td>
</tr>
<tr>
<td>id</td>
<td>String</td>
<td>Unique identifier for this result, 1-64 bytes</td>
</tr>
<tr>
<td>video_file_id</td>
<td>String</td>
<td>A valid file identifier for the video file</td>
</tr>
<tr>
<td>title</td>
<td>String</td>
<td>Title for the result</td>
</tr>
<tr>
<td>description</td>
<td>String</td>
<td><em>Optional</em>. Short description of the result</td>
</tr>
<tr>
<td>caption</td>
<td>String</td>
<td><em>Optional</em>. Caption of the video to be sent, 0-1024 characters after entities parsing</td>
</tr>
<tr>
<td>parse_mode</td>
<td>String</td>
<td><em>Optional</em>. Mode for parsing entities in the video caption. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>caption_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td><em>Optional</em>. List of special entities that appear in the caption, which can be specified instead of <em>parse_mode</em></td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a></td>
<td><em>Optional</em>. <a href="/bots#inline-keyboards-and-on-the-fly-updating">Inline keyboard</a> attached to the message</td>
</tr>
<tr>
<td>input_message_content</td>
<td><a href="#inputmessagecontent">InputMessageContent</a></td>
<td><em>Optional</em>. Content of the message to be sent instead of the video</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="inlinequeryresultcachedvoice" href="#inlinequeryresultcachedvoice"><i class="anchor-icon"></i></a>InlineQueryResultCachedVoice</h4>
<p>Represents a link to a voice message stored on the Telegram servers. By default, this voice message will be sent by the user. Alternatively, you can use <em>input_message_content</em> to send a message with the specified content instead of the voice message.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Type of the result, must be <em>voice</em></td>
</tr>
<tr>
<td>id</td>
<td>String</td>
<td>Unique identifier for this result, 1-64 bytes</td>
</tr>
<tr>
<td>voice_file_id</td>
<td>String</td>
<td>A valid file identifier for the voice message</td>
</tr>
<tr>
<td>title</td>
<td>String</td>
<td>Voice message title</td>
</tr>
<tr>
<td>caption</td>
<td>String</td>
<td><em>Optional</em>. Caption, 0-1024 characters after entities parsing</td>
</tr>
<tr>
<td>parse_mode</td>
<td>String</td>
<td><em>Optional</em>. Mode for parsing entities in the voice message caption. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>caption_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td><em>Optional</em>. List of special entities that appear in the caption, which can be specified instead of <em>parse_mode</em></td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a></td>
<td><em>Optional</em>. <a href="/bots#inline-keyboards-and-on-the-fly-updating">Inline keyboard</a> attached to the message</td>
</tr>
<tr>
<td>input_message_content</td>
<td><a href="#inputmessagecontent">InputMessageContent</a></td>
<td><em>Optional</em>. Content of the message to be sent instead of the voice message</td>
</tr>
</tbody>
</table>
<p><strong>Note:</strong> This will only work in Telegram versions released after 9 April, 2016. Older clients will ignore them.</p>
<h4><a class="anchor" name="inlinequeryresultcachedaudio" href="#inlinequeryresultcachedaudio"><i class="anchor-icon"></i></a>InlineQueryResultCachedAudio</h4>
<p>Represents a link to an MP3 audio file stored on the Telegram servers. By default, this audio file will be sent by the user. Alternatively, you can use <em>input_message_content</em> to send a message with the specified content instead of the audio.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Type of the result, must be <em>audio</em></td>
</tr>
<tr>
<td>id</td>
<td>String</td>
<td>Unique identifier for this result, 1-64 bytes</td>
</tr>
<tr>
<td>audio_file_id</td>
<td>String</td>
<td>A valid file identifier for the audio file</td>
</tr>
<tr>
<td>caption</td>
<td>String</td>
<td><em>Optional</em>. Caption, 0-1024 characters after entities parsing</td>
</tr>
<tr>
<td>parse_mode</td>
<td>String</td>
<td><em>Optional</em>. Mode for parsing entities in the audio caption. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>caption_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td><em>Optional</em>. List of special entities that appear in the caption, which can be specified instead of <em>parse_mode</em></td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a></td>
<td><em>Optional</em>. <a href="/bots#inline-keyboards-and-on-the-fly-updating">Inline keyboard</a> attached to the message</td>
</tr>
<tr>
<td>input_message_content</td>
<td><a href="#inputmessagecontent">InputMessageContent</a></td>
<td><em>Optional</em>. Content of the message to be sent instead of the audio</td>
</tr>
</tbody>
</table>
<p><strong>Note:</strong> This will only work in Telegram versions released after 9 April, 2016. Older clients will ignore them.</p>
<h4><a class="anchor" name="inputmessagecontent" href="#inputmessagecontent"><i class="anchor-icon"></i></a>InputMessageContent</h4>
<p>This object represents the content of a message to be sent as a result of an inline query. Telegram clients currently support the following 5 types:</p>
<ul>
<li><a href="#inputtextmessagecontent">InputTextMessageContent</a></li>
<li><a href="#inputlocationmessagecontent">InputLocationMessageContent</a></li>
<li><a href="#inputvenuemessagecontent">InputVenueMessageContent</a></li>
<li><a href="#inputcontactmessagecontent">InputContactMessageContent</a></li>
<li><a href="#inputinvoicemessagecontent">InputInvoiceMessageContent</a></li>
</ul>
<h4><a class="anchor" name="inputtextmessagecontent" href="#inputtextmessagecontent"><i class="anchor-icon"></i></a>InputTextMessageContent</h4>
<p>Represents the <a href="#inputmessagecontent">content</a> of a text message to be sent as the result of an inline query.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>message_text</td>
<td>String</td>
<td>Text of the message to be sent, 1-4096 characters</td>
</tr>
<tr>
<td>parse_mode</td>
<td>String</td>
<td><em>Optional</em>. Mode for parsing entities in the message text. See <a href="#formatting-options">formatting options</a> for more details.</td>
</tr>
<tr>
<td>entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td><em>Optional</em>. List of special entities that appear in message text, which can be specified instead of <em>parse_mode</em></td>
</tr>
<tr>
<td>disable_web_page_preview</td>
<td>Boolean</td>
<td><em>Optional</em>. Disables link previews for links in the sent message</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="inputlocationmessagecontent" href="#inputlocationmessagecontent"><i class="anchor-icon"></i></a>InputLocationMessageContent</h4>
<p>Represents the <a href="#inputmessagecontent">content</a> of a location message to be sent as the result of an inline query.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>latitude</td>
<td>Float</td>
<td>Latitude of the location in degrees</td>
</tr>
<tr>
<td>longitude</td>
<td>Float</td>
<td>Longitude of the location in degrees</td>
</tr>
<tr>
<td>horizontal_accuracy</td>
<td>Float number</td>
<td><em>Optional</em>. The radius of uncertainty for the location, measured in meters; 0-1500</td>
</tr>
<tr>
<td>live_period</td>
<td>Integer</td>
<td><em>Optional</em>. Period in seconds for which the location can be updated, should be between 60 and 86400.</td>
</tr>
<tr>
<td>heading</td>
<td>Integer</td>
<td><em>Optional</em>. For live locations, a direction in which the user is moving, in degrees. Must be between 1 and 360 if specified.</td>
</tr>
<tr>
<td>proximity_alert_radius</td>
<td>Integer</td>
<td><em>Optional</em>. For live locations, a maximum distance for proximity alerts about approaching another chat member, in meters. Must be between 1 and 100000 if specified.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="inputvenuemessagecontent" href="#inputvenuemessagecontent"><i class="anchor-icon"></i></a>InputVenueMessageContent</h4>
<p>Represents the <a href="#inputmessagecontent">content</a> of a venue message to be sent as the result of an inline query.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>latitude</td>
<td>Float</td>
<td>Latitude of the venue in degrees</td>
</tr>
<tr>
<td>longitude</td>
<td>Float</td>
<td>Longitude of the venue in degrees</td>
</tr>
<tr>
<td>title</td>
<td>String</td>
<td>Name of the venue</td>
</tr>
<tr>
<td>address</td>
<td>String</td>
<td>Address of the venue</td>
</tr>
<tr>
<td>foursquare_id</td>
<td>String</td>
<td><em>Optional</em>. Foursquare identifier of the venue, if known</td>
</tr>
<tr>
<td>foursquare_type</td>
<td>String</td>
<td><em>Optional</em>. Foursquare type of the venue, if known. (For example, “arts_entertainment/default”, “arts_entertainment/aquarium” or “food/icecream”.)</td>
</tr>
<tr>
<td>google_place_id</td>
<td>String</td>
<td><em>Optional</em>. Google Places identifier of the venue</td>
</tr>
<tr>
<td>google_place_type</td>
<td>String</td>
<td><em>Optional</em>. Google Places type of the venue. (See <a href="https://developers.google.com/places/web-service/supported_types">supported types</a>.)</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="inputcontactmessagecontent" href="#inputcontactmessagecontent"><i class="anchor-icon"></i></a>InputContactMessageContent</h4>
<p>Represents the <a href="#inputmessagecontent">content</a> of a contact message to be sent as the result of an inline query.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>phone_number</td>
<td>String</td>
<td>Contact&#39;s phone number</td>
</tr>
<tr>
<td>first_name</td>
<td>String</td>
<td>Contact&#39;s first name</td>
</tr>
<tr>
<td>last_name</td>
<td>String</td>
<td><em>Optional</em>. Contact&#39;s last name</td>
</tr>
<tr>
<td>vcard</td>
<td>String</td>
<td><em>Optional</em>. Additional data about the contact in the form of a <a href="https://en.wikipedia.org/wiki/VCard">vCard</a>, 0-2048 bytes</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="inputinvoicemessagecontent" href="#inputinvoicemessagecontent"><i class="anchor-icon"></i></a>InputInvoiceMessageContent</h4>
<p>Represents the <a href="#inputmessagecontent">content</a> of an invoice message to be sent as the result of an inline query.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>title</td>
<td>String</td>
<td>Product name, 1-32 characters</td>
</tr>
<tr>
<td>description</td>
<td>String</td>
<td>Product description, 1-255 characters</td>
</tr>
<tr>
<td>payload</td>
<td>String</td>
<td>Bot-defined invoice payload, 1-128 bytes. This will not be displayed to the user, use for your internal processes.</td>
</tr>
<tr>
<td>provider_token</td>
<td>String</td>
<td>Payment provider token, obtained via <a href="https://t.me/botfather">Botfather</a></td>
</tr>
<tr>
<td>currency</td>
<td>String</td>
<td>Three-letter ISO 4217 currency code, see <a href="/bots/payments#supported-currencies">more on currencies</a></td>
</tr>
<tr>
<td>prices</td>
<td>Array of <a href="#labeledprice">LabeledPrice</a></td>
<td>Price breakdown, a JSON-serialized list of components (e.g. product price, tax, discount, delivery cost, delivery tax, bonus, etc.)</td>
</tr>
<tr>
<td>max_tip_amount</td>
<td>Integer</td>
<td><em>Optional</em>. The maximum accepted amount for tips in the <em>smallest units</em> of the currency (integer, <strong>not</strong> float/double). For example, for a maximum tip of <code>US$ 1.45</code> pass <code>max_tip_amount = 145</code>. See the <em>exp</em> parameter in <a href="https://core.telegram.org/bots/payments/currencies.json">currencies.json</a>, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies). Defaults to 0</td>
</tr>
<tr>
<td>suggested_tip_amounts</td>
<td>Array of Integer</td>
<td><em>Optional</em>. A JSON-serialized array of suggested amounts of tip in the <em>smallest units</em> of the currency (integer, <strong>not</strong> float/double). At most 4 suggested tip amounts can be specified. The suggested tip amounts must be positive, passed in a strictly increased order and must not exceed <em>max_tip_amount</em>.</td>
</tr>
<tr>
<td>provider_data</td>
<td>String</td>
<td><em>Optional</em>. A JSON-serialized object for data about the invoice, which will be shared with the payment provider. A detailed description of the required fields should be provided by the payment provider.</td>
</tr>
<tr>
<td>photo_url</td>
<td>String</td>
<td><em>Optional</em>. URL of the product photo for the invoice. Can be a photo of the goods or a marketing image for a service. People like it better when they see what they are paying for.</td>
</tr>
<tr>
<td>photo_size</td>
<td>Integer</td>
<td><em>Optional</em>. Photo size</td>
</tr>
<tr>
<td>photo_width</td>
<td>Integer</td>
<td><em>Optional</em>. Photo width</td>
</tr>
<tr>
<td>photo_height</td>
<td>Integer</td>
<td><em>Optional</em>. Photo height</td>
</tr>
<tr>
<td>need_name</td>
<td>Boolean</td>
<td><em>Optional</em>. Pass <em>True</em>, if you require the user&#39;s full name to complete the order</td>
</tr>
<tr>
<td>need_phone_number</td>
<td>Boolean</td>
<td><em>Optional</em>. Pass <em>True</em>, if you require the user&#39;s phone number to complete the order</td>
</tr>
<tr>
<td>need_email</td>
<td>Boolean</td>
<td><em>Optional</em>. Pass <em>True</em>, if you require the user&#39;s email address to complete the order</td>
</tr>
<tr>
<td>need_shipping_address</td>
<td>Boolean</td>
<td><em>Optional</em>. Pass <em>True</em>, if you require the user&#39;s shipping address to complete the order</td>
</tr>
<tr>
<td>send_phone_number_to_provider</td>
<td>Boolean</td>
<td><em>Optional</em>. Pass <em>True</em>, if user&#39;s phone number should be sent to provider</td>
</tr>
<tr>
<td>send_email_to_provider</td>
<td>Boolean</td>
<td><em>Optional</em>. Pass <em>True</em>, if user&#39;s email address should be sent to provider</td>
</tr>
<tr>
<td>is_flexible</td>
<td>Boolean</td>
<td><em>Optional</em>. Pass <em>True</em>, if the final price depends on the shipping method</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="choseninlineresult" href="#choseninlineresult"><i class="anchor-icon"></i></a>ChosenInlineResult</h4>
<p>Represents a <a href="#inlinequeryresult">result</a> of an inline query that was chosen by the user and sent to their chat partner.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>result_id</td>
<td>String</td>
<td>The unique identifier for the result that was chosen</td>
</tr>
<tr>
<td>from</td>
<td><a href="#user">User</a></td>
<td>The user that chose the result</td>
</tr>
<tr>
<td>location</td>
<td><a href="#location">Location</a></td>
<td><em>Optional</em>. Sender location, only for bots that require user location</td>
</tr>
<tr>
<td>inline_message_id</td>
<td>String</td>
<td><em>Optional</em>. Identifier of the sent inline message. Available only if there is an <a href="#inlinekeyboardmarkup">inline keyboard</a> attached to the message. Will be also received in <a href="#callbackquery">callback queries</a> and can be used to <a href="#updating-messages">edit</a> the message.</td>
</tr>
<tr>
<td>query</td>
<td>String</td>
<td>The query that was used to obtain the result</td>
</tr>
</tbody>
</table>
<p><strong>Note:</strong> It is necessary to enable <a href="/bots/inline#collecting-feedback">inline feedback</a> via <a href="https://t.me/botfather">@Botfather</a> in order to receive these objects in updates.</p>
<h3><a class="anchor" name="payments" href="#payments"><i class="anchor-icon"></i></a>Payments</h3>
<p>Your bot can accept payments from Telegram users. Please see the <a href="/bots/payments">introduction to payments</a> for more details on the process and how to set up payments for your bot. Please note that users will need Telegram v.4.0 or higher to use payments (released on May 18, 2017).</p>
<h4><a class="anchor" name="sendinvoice" href="#sendinvoice"><i class="anchor-icon"></i></a>sendInvoice</h4>
<p>Use this method to send invoices. On success, the sent <a href="#message">Message</a> is returned.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer or String</td>
<td>Yes</td>
<td>Unique identifier for the target chat or username of the target channel (in the format <code>@channelusername</code>)</td>
</tr>
<tr>
<td>title</td>
<td>String</td>
<td>Yes</td>
<td>Product name, 1-32 characters</td>
</tr>
<tr>
<td>description</td>
<td>String</td>
<td>Yes</td>
<td>Product description, 1-255 characters</td>
</tr>
<tr>
<td>payload</td>
<td>String</td>
<td>Yes</td>
<td>Bot-defined invoice payload, 1-128 bytes. This will not be displayed to the user, use for your internal processes.</td>
</tr>
<tr>
<td>provider_token</td>
<td>String</td>
<td>Yes</td>
<td>Payments provider token, obtained via <a href="https://t.me/botfather">Botfather</a></td>
</tr>
<tr>
<td>currency</td>
<td>String</td>
<td>Yes</td>
<td>Three-letter ISO 4217 currency code, see <a href="/bots/payments#supported-currencies">more on currencies</a></td>
</tr>
<tr>
<td>prices</td>
<td>Array of <a href="#labeledprice">LabeledPrice</a></td>
<td>Yes</td>
<td>Price breakdown, a JSON-serialized list of components (e.g. product price, tax, discount, delivery cost, delivery tax, bonus, etc.)</td>
</tr>
<tr>
<td>max_tip_amount</td>
<td>Integer</td>
<td>Optional</td>
<td>The maximum accepted amount for tips in the <em>smallest units</em> of the currency (integer, <strong>not</strong> float/double). For example, for a maximum tip of <code>US$ 1.45</code> pass <code>max_tip_amount = 145</code>. See the <em>exp</em> parameter in <a href="https://core.telegram.org/bots/payments/currencies.json">currencies.json</a>, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies). Defaults to 0</td>
</tr>
<tr>
<td>suggested_tip_amounts</td>
<td>Array of Integer</td>
<td>Optional</td>
<td>A JSON-serialized array of suggested amounts of tips in the <em>smallest units</em> of the currency (integer, <strong>not</strong> float/double). At most 4 suggested tip amounts can be specified. The suggested tip amounts must be positive, passed in a strictly increased order and must not exceed <em>max_tip_amount</em>.</td>
</tr>
<tr>
<td>start_parameter</td>
<td>String</td>
<td>Optional</td>
<td>Unique deep-linking parameter. If left empty, <strong>forwarded copies</strong> of the sent message will have a <em>Pay</em> button, allowing multiple users to pay directly from the forwarded message, using the same invoice. If non-empty, forwarded copies of the sent message will have a <em>URL</em> button with a deep link to the bot (instead of a <em>Pay</em> button), with the value used as the start parameter</td>
</tr>
<tr>
<td>provider_data</td>
<td>String</td>
<td>Optional</td>
<td>A JSON-serialized data about the invoice, which will be shared with the payment provider. A detailed description of required fields should be provided by the payment provider.</td>
</tr>
<tr>
<td>photo_url</td>
<td>String</td>
<td>Optional</td>
<td>URL of the product photo for the invoice. Can be a photo of the goods or a marketing image for a service. People like it better when they see what they are paying for.</td>
</tr>
<tr>
<td>photo_size</td>
<td>Integer</td>
<td>Optional</td>
<td>Photo size</td>
</tr>
<tr>
<td>photo_width</td>
<td>Integer</td>
<td>Optional</td>
<td>Photo width</td>
</tr>
<tr>
<td>photo_height</td>
<td>Integer</td>
<td>Optional</td>
<td>Photo height</td>
</tr>
<tr>
<td>need_name</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if you require the user&#39;s full name to complete the order</td>
</tr>
<tr>
<td>need_phone_number</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if you require the user&#39;s phone number to complete the order</td>
</tr>
<tr>
<td>need_email</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if you require the user&#39;s email address to complete the order</td>
</tr>
<tr>
<td>need_shipping_address</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if you require the user&#39;s shipping address to complete the order</td>
</tr>
<tr>
<td>send_phone_number_to_provider</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if user&#39;s phone number should be sent to provider</td>
</tr>
<tr>
<td>send_email_to_provider</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if user&#39;s email address should be sent to provider</td>
</tr>
<tr>
<td>is_flexible</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the final price depends on the shipping method</td>
</tr>
<tr>
<td>disable_notification</td>
<td>Boolean</td>
<td>Optional</td>
<td>Sends the message <a href="https://telegram.org/blog/channels-2-0#silent-messages">silently</a>. Users will receive a notification with no sound.</td>
</tr>
<tr>
<td>protect_content</td>
<td>Boolean</td>
<td>Optional</td>
<td>Protects the contents of the sent message from forwarding and saving</td>
</tr>
<tr>
<td>reply_to_message_id</td>
<td>Integer</td>
<td>Optional</td>
<td>If the message is a reply, ID of the original message</td>
</tr>
<tr>
<td>allow_sending_without_reply</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the message should be sent even if the specified replied-to message is not found</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a></td>
<td>Optional</td>
<td>A JSON-serialized object for an <a href="https://core.telegram.org/bots#inline-keyboards-and-on-the-fly-updating">inline keyboard</a>. If empty, one &#39;Pay <code>total price</code>&#39; button will be shown. If not empty, the first button must be a Pay button.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="answershippingquery" href="#answershippingquery"><i class="anchor-icon"></i></a>answerShippingQuery</h4>
<p>If you sent an invoice requesting a shipping address and the parameter <em>is_flexible</em> was specified, the Bot API will send an <a href="#update">Update</a> with a <em>shipping_query</em> field to the bot. Use this method to reply to shipping queries. On success, <em>True</em> is returned.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>shipping_query_id</td>
<td>String</td>
<td>Yes</td>
<td>Unique identifier for the query to be answered</td>
</tr>
<tr>
<td>ok</td>
<td>Boolean</td>
<td>Yes</td>
<td>Specify <em>True</em> if delivery to the specified address is possible and False if there are any problems (for example, if delivery to the specified address is not possible)</td>
</tr>
<tr>
<td>shipping_options</td>
<td>Array of <a href="#shippingoption">ShippingOption</a></td>
<td>Optional</td>
<td>Required if <em>ok</em> is <em>True</em>. A JSON-serialized array of available shipping options.</td>
</tr>
<tr>
<td>error_message</td>
<td>String</td>
<td>Optional</td>
<td>Required if <em>ok</em> is False. Error message in human readable form that explains why it is impossible to complete the order (e.g. &quot;Sorry, delivery to your desired address is unavailable&#39;). Telegram will display this message to the user.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="answerprecheckoutquery" href="#answerprecheckoutquery"><i class="anchor-icon"></i></a>answerPreCheckoutQuery</h4>
<p>Once the user has confirmed their payment and shipping details, the Bot API sends the final confirmation in the form of an <a href="#update">Update</a> with the field <em>pre_checkout_query</em>. Use this method to respond to such pre-checkout queries. On success, <em>True</em> is returned. <strong>Note:</strong> The Bot API must receive an answer within 10 seconds after the pre-checkout query was sent.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>pre_checkout_query_id</td>
<td>String</td>
<td>Yes</td>
<td>Unique identifier for the query to be answered</td>
</tr>
<tr>
<td>ok</td>
<td>Boolean</td>
<td>Yes</td>
<td>Specify <em>True</em> if everything is alright (goods are available, etc.) and the bot is ready to proceed with the order. Use <em>False</em> if there are any problems.</td>
</tr>
<tr>
<td>error_message</td>
<td>String</td>
<td>Optional</td>
<td>Required if <em>ok</em> is <em>False</em>. Error message in human readable form that explains the reason for failure to proceed with the checkout (e.g. &quot;Sorry, somebody just bought the last of our amazing black T-shirts while you were busy filling out your payment details. Please choose a different color or garment!&quot;). Telegram will display this message to the user.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="labeledprice" href="#labeledprice"><i class="anchor-icon"></i></a>LabeledPrice</h4>
<p>This object represents a portion of the price for goods or services.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>label</td>
<td>String</td>
<td>Portion label</td>
</tr>
<tr>
<td>amount</td>
<td>Integer</td>
<td>Price of the product in the <em>smallest units</em> of the <a href="/bots/payments#supported-currencies">currency</a> (integer, <strong>not</strong> float/double). For example, for a price of <code>US$ 1.45</code> pass <code>amount = 145</code>. See the <em>exp</em> parameter in <a href="https://core.telegram.org/bots/payments/currencies.json">currencies.json</a>, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies).</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="invoice" href="#invoice"><i class="anchor-icon"></i></a>Invoice</h4>
<p>This object contains basic information about an invoice.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>title</td>
<td>String</td>
<td>Product name</td>
</tr>
<tr>
<td>description</td>
<td>String</td>
<td>Product description</td>
</tr>
<tr>
<td>start_parameter</td>
<td>String</td>
<td>Unique bot deep-linking parameter that can be used to generate this invoice</td>
</tr>
<tr>
<td>currency</td>
<td>String</td>
<td>Three-letter ISO 4217 <a href="/bots/payments#supported-currencies">currency</a> code</td>
</tr>
<tr>
<td>total_amount</td>
<td>Integer</td>
<td>Total price in the <em>smallest units</em> of the currency (integer, <strong>not</strong> float/double). For example, for a price of <code>US$ 1.45</code> pass <code>amount = 145</code>. See the <em>exp</em> parameter in <a href="https://core.telegram.org/bots/payments/currencies.json">currencies.json</a>, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies).</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="shippingaddress" href="#shippingaddress"><i class="anchor-icon"></i></a>ShippingAddress</h4>
<p>This object represents a shipping address.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>country_code</td>
<td>String</td>
<td>ISO 3166-1 alpha-2 country code</td>
</tr>
<tr>
<td>state</td>
<td>String</td>
<td>State, if applicable</td>
</tr>
<tr>
<td>city</td>
<td>String</td>
<td>City</td>
</tr>
<tr>
<td>street_line1</td>
<td>String</td>
<td>First line for the address</td>
</tr>
<tr>
<td>street_line2</td>
<td>String</td>
<td>Second line for the address</td>
</tr>
<tr>
<td>post_code</td>
<td>String</td>
<td>Address post code</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="orderinfo" href="#orderinfo"><i class="anchor-icon"></i></a>OrderInfo</h4>
<p>This object represents information about an order.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>name</td>
<td>String</td>
<td><em>Optional</em>. User name</td>
</tr>
<tr>
<td>phone_number</td>
<td>String</td>
<td><em>Optional</em>. User&#39;s phone number</td>
</tr>
<tr>
<td>email</td>
<td>String</td>
<td><em>Optional</em>. User email</td>
</tr>
<tr>
<td>shipping_address</td>
<td><a href="#shippingaddress">ShippingAddress</a></td>
<td><em>Optional</em>. User shipping address</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="shippingoption" href="#shippingoption"><i class="anchor-icon"></i></a>ShippingOption</h4>
<p>This object represents one shipping option.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>id</td>
<td>String</td>
<td>Shipping option identifier</td>
</tr>
<tr>
<td>title</td>
<td>String</td>
<td>Option title</td>
</tr>
<tr>
<td>prices</td>
<td>Array of <a href="#labeledprice">LabeledPrice</a></td>
<td>List of price portions</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="successfulpayment" href="#successfulpayment"><i class="anchor-icon"></i></a>SuccessfulPayment</h4>
<p>This object contains basic information about a successful payment.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>currency</td>
<td>String</td>
<td>Three-letter ISO 4217 <a href="/bots/payments#supported-currencies">currency</a> code</td>
</tr>
<tr>
<td>total_amount</td>
<td>Integer</td>
<td>Total price in the <em>smallest units</em> of the currency (integer, <strong>not</strong> float/double). For example, for a price of <code>US$ 1.45</code> pass <code>amount = 145</code>. See the <em>exp</em> parameter in <a href="https://core.telegram.org/bots/payments/currencies.json">currencies.json</a>, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies).</td>
</tr>
<tr>
<td>invoice_payload</td>
<td>String</td>
<td>Bot specified invoice payload</td>
</tr>
<tr>
<td>shipping_option_id</td>
<td>String</td>
<td><em>Optional</em>. Identifier of the shipping option chosen by the user</td>
</tr>
<tr>
<td>order_info</td>
<td><a href="#orderinfo">OrderInfo</a></td>
<td><em>Optional</em>. Order info provided by the user</td>
</tr>
<tr>
<td>telegram_payment_charge_id</td>
<td>String</td>
<td>Telegram payment identifier</td>
</tr>
<tr>
<td>provider_payment_charge_id</td>
<td>String</td>
<td>Provider payment identifier</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="shippingquery" href="#shippingquery"><i class="anchor-icon"></i></a>ShippingQuery</h4>
<p>This object contains information about an incoming shipping query.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>id</td>
<td>String</td>
<td>Unique query identifier</td>
</tr>
<tr>
<td>from</td>
<td><a href="#user">User</a></td>
<td>User who sent the query</td>
</tr>
<tr>
<td>invoice_payload</td>
<td>String</td>
<td>Bot specified invoice payload</td>
</tr>
<tr>
<td>shipping_address</td>
<td><a href="#shippingaddress">ShippingAddress</a></td>
<td>User specified shipping address</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="precheckoutquery" href="#precheckoutquery"><i class="anchor-icon"></i></a>PreCheckoutQuery</h4>
<p>This object contains information about an incoming pre-checkout query.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>id</td>
<td>String</td>
<td>Unique query identifier</td>
</tr>
<tr>
<td>from</td>
<td><a href="#user">User</a></td>
<td>User who sent the query</td>
</tr>
<tr>
<td>currency</td>
<td>String</td>
<td>Three-letter ISO 4217 <a href="/bots/payments#supported-currencies">currency</a> code</td>
</tr>
<tr>
<td>total_amount</td>
<td>Integer</td>
<td>Total price in the <em>smallest units</em> of the currency (integer, <strong>not</strong> float/double). For example, for a price of <code>US$ 1.45</code> pass <code>amount = 145</code>. See the <em>exp</em> parameter in <a href="https://core.telegram.org/bots/payments/currencies.json">currencies.json</a>, it shows the number of digits past the decimal point for each currency (2 for the majority of currencies).</td>
</tr>
<tr>
<td>invoice_payload</td>
<td>String</td>
<td>Bot specified invoice payload</td>
</tr>
<tr>
<td>shipping_option_id</td>
<td>String</td>
<td><em>Optional</em>. Identifier of the shipping option chosen by the user</td>
</tr>
<tr>
<td>order_info</td>
<td><a href="#orderinfo">OrderInfo</a></td>
<td><em>Optional</em>. Order info provided by the user</td>
</tr>
</tbody>
</table>
<h3><a class="anchor" name="telegram-passport" href="#telegram-passport"><i class="anchor-icon"></i></a>Telegram Passport</h3>
<p><strong>Telegram Passport</strong> is a unified authorization method for services that require personal identification. Users can upload their documents once, then instantly share their data with services that require real-world ID (finance, ICOs, etc.). Please see the <a href="/passport">manual</a> for details.</p>
<h4><a class="anchor" name="passportdata" href="#passportdata"><i class="anchor-icon"></i></a>PassportData</h4>
<p>Contains information about Telegram Passport data shared with the bot by the user.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>data</td>
<td>Array of <a href="#encryptedpassportelement">EncryptedPassportElement</a></td>
<td>Array with information about documents and other Telegram Passport elements that was shared with the bot</td>
</tr>
<tr>
<td>credentials</td>
<td><a href="#encryptedcredentials">EncryptedCredentials</a></td>
<td>Encrypted credentials required to decrypt the data</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="passportfile" href="#passportfile"><i class="anchor-icon"></i></a>PassportFile</h4>
<p>This object represents a file uploaded to Telegram Passport. Currently all Telegram Passport files are in JPEG format when decrypted and don&#39;t exceed 10MB.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>file_id</td>
<td>String</td>
<td>Identifier for this file, which can be used to download or reuse the file</td>
</tr>
<tr>
<td>file_unique_id</td>
<td>String</td>
<td>Unique identifier for this file, which is supposed to be the same over time and for different bots. Can&#39;t be used to download or reuse the file.</td>
</tr>
<tr>
<td>file_size</td>
<td>Integer</td>
<td>File size in bytes</td>
</tr>
<tr>
<td>file_date</td>
<td>Integer</td>
<td>Unix time when the file was uploaded</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="encryptedpassportelement" href="#encryptedpassportelement"><i class="anchor-icon"></i></a>EncryptedPassportElement</h4>
<p>Contains information about documents or other Telegram Passport elements shared with the bot by the user.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>type</td>
<td>String</td>
<td>Element type. One of “personal_details”, “passport”, “driver_license”, “identity_card”, “internal_passport”, “address”, “utility_bill”, “bank_statement”, “rental_agreement”, “passport_registration”, “temporary_registration”, “phone_number”, “email”.</td>
</tr>
<tr>
<td>data</td>
<td>String</td>
<td><em>Optional</em>. Base64-encoded encrypted Telegram Passport element data provided by the user, available for “personal_details”, “passport”, “driver_license”, “identity_card”, “internal_passport” and “address” types. Can be decrypted and verified using the accompanying <a href="#encryptedcredentials">EncryptedCredentials</a>.</td>
</tr>
<tr>
<td>phone_number</td>
<td>String</td>
<td><em>Optional</em>. User&#39;s verified phone number, available only for “phone_number” type</td>
</tr>
<tr>
<td>email</td>
<td>String</td>
<td><em>Optional</em>. User&#39;s verified email address, available only for “email” type</td>
</tr>
<tr>
<td>files</td>
<td>Array of <a href="#passportfile">PassportFile</a></td>
<td><em>Optional</em>. Array of encrypted files with documents provided by the user, available for “utility_bill”, “bank_statement”, “rental_agreement”, “passport_registration” and “temporary_registration” types. Files can be decrypted and verified using the accompanying <a href="#encryptedcredentials">EncryptedCredentials</a>.</td>
</tr>
<tr>
<td>front_side</td>
<td><a href="#passportfile">PassportFile</a></td>
<td><em>Optional</em>. Encrypted file with the front side of the document, provided by the user. Available for “passport”, “driver_license”, “identity_card” and “internal_passport”. The file can be decrypted and verified using the accompanying <a href="#encryptedcredentials">EncryptedCredentials</a>.</td>
</tr>
<tr>
<td>reverse_side</td>
<td><a href="#passportfile">PassportFile</a></td>
<td><em>Optional</em>. Encrypted file with the reverse side of the document, provided by the user. Available for “driver_license” and “identity_card”. The file can be decrypted and verified using the accompanying <a href="#encryptedcredentials">EncryptedCredentials</a>.</td>
</tr>
<tr>
<td>selfie</td>
<td><a href="#passportfile">PassportFile</a></td>
<td><em>Optional</em>. Encrypted file with the selfie of the user holding a document, provided by the user; available for “passport”, “driver_license”, “identity_card” and “internal_passport”. The file can be decrypted and verified using the accompanying <a href="#encryptedcredentials">EncryptedCredentials</a>.</td>
</tr>
<tr>
<td>translation</td>
<td>Array of <a href="#passportfile">PassportFile</a></td>
<td><em>Optional</em>. Array of encrypted files with translated versions of documents provided by the user. Available if requested for “passport”, “driver_license”, “identity_card”, “internal_passport”, “utility_bill”, “bank_statement”, “rental_agreement”, “passport_registration” and “temporary_registration” types. Files can be decrypted and verified using the accompanying <a href="#encryptedcredentials">EncryptedCredentials</a>.</td>
</tr>
<tr>
<td>hash</td>
<td>String</td>
<td>Base64-encoded element hash for using in <a href="#passportelementerrorunspecified">PassportElementErrorUnspecified</a></td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="encryptedcredentials" href="#encryptedcredentials"><i class="anchor-icon"></i></a>EncryptedCredentials</h4>
<p>Contains data required for decrypting and authenticating <a href="#encryptedpassportelement">EncryptedPassportElement</a>. See the <a href="https://core.telegram.org/passport#receiving-information">Telegram Passport Documentation</a> for a complete description of the data decryption and authentication processes.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>data</td>
<td>String</td>
<td>Base64-encoded encrypted JSON-serialized data with unique user&#39;s payload, data hashes and secrets required for <a href="#encryptedpassportelement">EncryptedPassportElement</a> decryption and authentication</td>
</tr>
<tr>
<td>hash</td>
<td>String</td>
<td>Base64-encoded data hash for data authentication</td>
</tr>
<tr>
<td>secret</td>
<td>String</td>
<td>Base64-encoded secret, encrypted with the bot&#39;s public RSA key, required for data decryption</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="setpassportdataerrors" href="#setpassportdataerrors"><i class="anchor-icon"></i></a>setPassportDataErrors</h4>
<p>Informs a user that some of the Telegram Passport elements they provided contains errors. The user will not be able to re-submit their Passport to you until the errors are fixed (the contents of the field for which you returned the error must change). Returns <em>True</em> on success.</p>
<p>Use this if the data submitted by the user doesn&#39;t satisfy the standards your service requires for any reason. For example, if a birthday date seems invalid, a submitted document is blurry, a scan shows evidence of tampering, etc. Supply some details in the error message to make sure the user knows how to correct the issues.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>user_id</td>
<td>Integer</td>
<td>Yes</td>
<td>User identifier</td>
</tr>
<tr>
<td>errors</td>
<td>Array of <a href="#passportelementerror">PassportElementError</a></td>
<td>Yes</td>
<td>A JSON-serialized array describing the errors</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="passportelementerror" href="#passportelementerror"><i class="anchor-icon"></i></a>PassportElementError</h4>
<p>This object represents an error in the Telegram Passport element which was submitted that should be resolved by the user. It should be one of:</p>
<ul>
<li><a href="#passportelementerrordatafield">PassportElementErrorDataField</a></li>
<li><a href="#passportelementerrorfrontside">PassportElementErrorFrontSide</a></li>
<li><a href="#passportelementerrorreverseside">PassportElementErrorReverseSide</a></li>
<li><a href="#passportelementerrorselfie">PassportElementErrorSelfie</a></li>
<li><a href="#passportelementerrorfile">PassportElementErrorFile</a></li>
<li><a href="#passportelementerrorfiles">PassportElementErrorFiles</a></li>
<li><a href="#passportelementerrortranslationfile">PassportElementErrorTranslationFile</a></li>
<li><a href="#passportelementerrortranslationfiles">PassportElementErrorTranslationFiles</a></li>
<li><a href="#passportelementerrorunspecified">PassportElementErrorUnspecified</a></li>
</ul>
<h4><a class="anchor" name="passportelementerrordatafield" href="#passportelementerrordatafield"><i class="anchor-icon"></i></a>PassportElementErrorDataField</h4>
<p>Represents an issue in one of the data fields that was provided by the user. The error is considered resolved when the field&#39;s value changes.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>source</td>
<td>String</td>
<td>Error source, must be <em>data</em></td>
</tr>
<tr>
<td>type</td>
<td>String</td>
<td>The section of the user&#39;s Telegram Passport which has the error, one of “personal_details”, “passport”, “driver_license”, “identity_card”, “internal_passport”, “address”</td>
</tr>
<tr>
<td>field_name</td>
<td>String</td>
<td>Name of the data field which has the error</td>
</tr>
<tr>
<td>data_hash</td>
<td>String</td>
<td>Base64-encoded data hash</td>
</tr>
<tr>
<td>message</td>
<td>String</td>
<td>Error message</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="passportelementerrorfrontside" href="#passportelementerrorfrontside"><i class="anchor-icon"></i></a>PassportElementErrorFrontSide</h4>
<p>Represents an issue with the front side of a document. The error is considered resolved when the file with the front side of the document changes.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>source</td>
<td>String</td>
<td>Error source, must be <em>front_side</em></td>
</tr>
<tr>
<td>type</td>
<td>String</td>
<td>The section of the user&#39;s Telegram Passport which has the issue, one of “passport”, “driver_license”, “identity_card”, “internal_passport”</td>
</tr>
<tr>
<td>file_hash</td>
<td>String</td>
<td>Base64-encoded hash of the file with the front side of the document</td>
</tr>
<tr>
<td>message</td>
<td>String</td>
<td>Error message</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="passportelementerrorreverseside" href="#passportelementerrorreverseside"><i class="anchor-icon"></i></a>PassportElementErrorReverseSide</h4>
<p>Represents an issue with the reverse side of a document. The error is considered resolved when the file with reverse side of the document changes.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>source</td>
<td>String</td>
<td>Error source, must be <em>reverse_side</em></td>
</tr>
<tr>
<td>type</td>
<td>String</td>
<td>The section of the user&#39;s Telegram Passport which has the issue, one of “driver_license”, “identity_card”</td>
</tr>
<tr>
<td>file_hash</td>
<td>String</td>
<td>Base64-encoded hash of the file with the reverse side of the document</td>
</tr>
<tr>
<td>message</td>
<td>String</td>
<td>Error message</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="passportelementerrorselfie" href="#passportelementerrorselfie"><i class="anchor-icon"></i></a>PassportElementErrorSelfie</h4>
<p>Represents an issue with the selfie with a document. The error is considered resolved when the file with the selfie changes.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>source</td>
<td>String</td>
<td>Error source, must be <em>selfie</em></td>
</tr>
<tr>
<td>type</td>
<td>String</td>
<td>The section of the user&#39;s Telegram Passport which has the issue, one of “passport”, “driver_license”, “identity_card”, “internal_passport”</td>
</tr>
<tr>
<td>file_hash</td>
<td>String</td>
<td>Base64-encoded hash of the file with the selfie</td>
</tr>
<tr>
<td>message</td>
<td>String</td>
<td>Error message</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="passportelementerrorfile" href="#passportelementerrorfile"><i class="anchor-icon"></i></a>PassportElementErrorFile</h4>
<p>Represents an issue with a document scan. The error is considered resolved when the file with the document scan changes.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>source</td>
<td>String</td>
<td>Error source, must be <em>file</em></td>
</tr>
<tr>
<td>type</td>
<td>String</td>
<td>The section of the user&#39;s Telegram Passport which has the issue, one of “utility_bill”, “bank_statement”, “rental_agreement”, “passport_registration”, “temporary_registration”</td>
</tr>
<tr>
<td>file_hash</td>
<td>String</td>
<td>Base64-encoded file hash</td>
</tr>
<tr>
<td>message</td>
<td>String</td>
<td>Error message</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="passportelementerrorfiles" href="#passportelementerrorfiles"><i class="anchor-icon"></i></a>PassportElementErrorFiles</h4>
<p>Represents an issue with a list of scans. The error is considered resolved when the list of files containing the scans changes.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>source</td>
<td>String</td>
<td>Error source, must be <em>files</em></td>
</tr>
<tr>
<td>type</td>
<td>String</td>
<td>The section of the user&#39;s Telegram Passport which has the issue, one of “utility_bill”, “bank_statement”, “rental_agreement”, “passport_registration”, “temporary_registration”</td>
</tr>
<tr>
<td>file_hashes</td>
<td>Array of String</td>
<td>List of base64-encoded file hashes</td>
</tr>
<tr>
<td>message</td>
<td>String</td>
<td>Error message</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="passportelementerrortranslationfile" href="#passportelementerrortranslationfile"><i class="anchor-icon"></i></a>PassportElementErrorTranslationFile</h4>
<p>Represents an issue with one of the files that constitute the translation of a document. The error is considered resolved when the file changes.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>source</td>
<td>String</td>
<td>Error source, must be <em>translation_file</em></td>
</tr>
<tr>
<td>type</td>
<td>String</td>
<td>Type of element of the user&#39;s Telegram Passport which has the issue, one of “passport”, “driver_license”, “identity_card”, “internal_passport”, “utility_bill”, “bank_statement”, “rental_agreement”, “passport_registration”, “temporary_registration”</td>
</tr>
<tr>
<td>file_hash</td>
<td>String</td>
<td>Base64-encoded file hash</td>
</tr>
<tr>
<td>message</td>
<td>String</td>
<td>Error message</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="passportelementerrortranslationfiles" href="#passportelementerrortranslationfiles"><i class="anchor-icon"></i></a>PassportElementErrorTranslationFiles</h4>
<p>Represents an issue with the translated version of a document. The error is considered resolved when a file with the document translation change.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>source</td>
<td>String</td>
<td>Error source, must be <em>translation_files</em></td>
</tr>
<tr>
<td>type</td>
<td>String</td>
<td>Type of element of the user&#39;s Telegram Passport which has the issue, one of “passport”, “driver_license”, “identity_card”, “internal_passport”, “utility_bill”, “bank_statement”, “rental_agreement”, “passport_registration”, “temporary_registration”</td>
</tr>
<tr>
<td>file_hashes</td>
<td>Array of String</td>
<td>List of base64-encoded file hashes</td>
</tr>
<tr>
<td>message</td>
<td>String</td>
<td>Error message</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="passportelementerrorunspecified" href="#passportelementerrorunspecified"><i class="anchor-icon"></i></a>PassportElementErrorUnspecified</h4>
<p>Represents an issue in an unspecified place. The error is considered resolved when new data is added.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>source</td>
<td>String</td>
<td>Error source, must be <em>unspecified</em></td>
</tr>
<tr>
<td>type</td>
<td>String</td>
<td>Type of element of the user&#39;s Telegram Passport which has the issue</td>
</tr>
<tr>
<td>element_hash</td>
<td>String</td>
<td>Base64-encoded element hash</td>
</tr>
<tr>
<td>message</td>
<td>String</td>
<td>Error message</td>
</tr>
</tbody>
</table>
<h3><a class="anchor" name="games" href="#games"><i class="anchor-icon"></i></a>Games</h3>
<p>Your bot can offer users <strong>HTML5 games</strong> to play solo or to compete against each other in groups and one-on-one chats. Create games via <a href="https://t.me/botfather">@BotFather</a> using the <em>/newgame</em> command. Please note that this kind of power requires responsibility: you will need to accept the terms for each game that your bots will be offering.</p>
<ul>
<li>Games are a new type of content on Telegram, represented by the <a href="#game">Game</a> and <a href="#inlinequeryresultgame">InlineQueryResultGame</a> objects.</li>
<li>Once you&#39;ve created a game via <a href="https://t.me/botfather">BotFather</a>, you can send games to chats as regular messages using the <a href="#sendgame">sendGame</a> method, or use <a href="#inline-mode">inline mode</a> with <a href="#inlinequeryresultgame">InlineQueryResultGame</a>.</li>
<li>If you send the game message without any buttons, it will automatically have a &#39;Play <em>GameName</em>&#39; button. When this button is pressed, your bot gets a <a href="#callbackquery">CallbackQuery</a> with the <em>game_short_name</em> of the requested game. You provide the correct URL for this particular user and the app opens the game in the in-app browser.</li>
<li>You can manually add multiple buttons to your game message. Please note that the first button in the first row <strong>must always</strong> launch the game, using the field <em>callback_game</em> in <a href="#inlinekeyboardbutton">InlineKeyboardButton</a>. You can add extra buttons according to taste: e.g., for a description of the rules, or to open the game&#39;s official community.</li>
<li>To make your game more attractive, you can upload a GIF animation that demostrates the game to the users via <a href="https://t.me/botfather">BotFather</a> (see <a href="https://t.me/gamebot?game=lumberjack">Lumberjack</a> for example).</li>
<li>A game message will also display high scores for the current chat. Use <a href="#setgamescore">setGameScore</a> to post high scores to the chat with the game, add the <em>edit_message</em> parameter to automatically update the message with the current scoreboard.</li>
<li>Use <a href="#getgamehighscores">getGameHighScores</a> to get data for in-game high score tables.</li>
<li>You can also add an extra <a href="/bots/games#sharing-your-game-to-telegram-chats">sharing button</a> for users to share their best score to different chats.</li>
<li>For examples of what can be done using this new stuff, check the <a href="https://t.me/gamebot">@gamebot</a> and <a href="https://t.me/gamee">@gamee</a> bots.</li>
</ul>
<h4><a class="anchor" name="sendgame" href="#sendgame"><i class="anchor-icon"></i></a>sendGame</h4>
<p>Use this method to send a game. On success, the sent <a href="#message">Message</a> is returned.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>chat_id</td>
<td>Integer</td>
<td>Yes</td>
<td>Unique identifier for the target chat</td>
</tr>
<tr>
<td>game_short_name</td>
<td>String</td>
<td>Yes</td>
<td>Short name of the game, serves as the unique identifier for the game. Set up your games via <a href="https://t.me/botfather">Botfather</a>.</td>
</tr>
<tr>
<td>disable_notification</td>
<td>Boolean</td>
<td>Optional</td>
<td>Sends the message <a href="https://telegram.org/blog/channels-2-0#silent-messages">silently</a>. Users will receive a notification with no sound.</td>
</tr>
<tr>
<td>protect_content</td>
<td>Boolean</td>
<td>Optional</td>
<td>Protects the contents of the sent message from forwarding and saving</td>
</tr>
<tr>
<td>reply_to_message_id</td>
<td>Integer</td>
<td>Optional</td>
<td>If the message is a reply, ID of the original message</td>
</tr>
<tr>
<td>allow_sending_without_reply</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the message should be sent even if the specified replied-to message is not found</td>
</tr>
<tr>
<td>reply_markup</td>
<td><a href="#inlinekeyboardmarkup">InlineKeyboardMarkup</a></td>
<td>Optional</td>
<td>A JSON-serialized object for an <a href="https://core.telegram.org/bots#inline-keyboards-and-on-the-fly-updating">inline keyboard</a>. If empty, one &#39;Play game_title&#39; button will be shown. If not empty, the first button must launch the game.</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="game" href="#game"><i class="anchor-icon"></i></a>Game</h4>
<p>This object represents a game. Use BotFather to create and edit games, their short names will act as unique identifiers.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>title</td>
<td>String</td>
<td>Title of the game</td>
</tr>
<tr>
<td>description</td>
<td>String</td>
<td>Description of the game</td>
</tr>
<tr>
<td>photo</td>
<td>Array of <a href="#photosize">PhotoSize</a></td>
<td>Photo that will be displayed in the game message in chats.</td>
</tr>
<tr>
<td>text</td>
<td>String</td>
<td><em>Optional</em>. Brief description of the game or high scores included in the game message. Can be automatically edited to include current high scores for the game when the bot calls <a href="#setgamescore">setGameScore</a>, or manually edited using <a href="#editmessagetext">editMessageText</a>. 0-4096 characters.</td>
</tr>
<tr>
<td>text_entities</td>
<td>Array of <a href="#messageentity">MessageEntity</a></td>
<td><em>Optional</em>. Special entities that appear in <em>text</em>, such as usernames, URLs, bot commands, etc.</td>
</tr>
<tr>
<td>animation</td>
<td><a href="#animation">Animation</a></td>
<td><em>Optional</em>. Animation that will be displayed in the game message in chats. Upload via <a href="https://t.me/botfather">BotFather</a></td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="callbackgame" href="#callbackgame"><i class="anchor-icon"></i></a>CallbackGame</h4>
<p>A placeholder, currently holds no information. Use <a href="https://t.me/botfather">BotFather</a> to set up your game.</p>
<h4><a class="anchor" name="setgamescore" href="#setgamescore"><i class="anchor-icon"></i></a>setGameScore</h4>
<p>Use this method to set the score of the specified user in a game message. On success, if the message is not an inline message, the <a href="#message">Message</a> is returned, otherwise <em>True</em> is returned. Returns an error, if the new score is not greater than the user&#39;s current score in the chat and <em>force</em> is <em>False</em>.</p>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>user_id</td>
<td>Integer</td>
<td>Yes</td>
<td>User identifier</td>
</tr>
<tr>
<td>score</td>
<td>Integer</td>
<td>Yes</td>
<td>New score, must be non-negative</td>
</tr>
<tr>
<td>force</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the high score is allowed to decrease. This can be useful when fixing mistakes or banning cheaters</td>
</tr>
<tr>
<td>disable_edit_message</td>
<td>Boolean</td>
<td>Optional</td>
<td>Pass <em>True</em>, if the game message should not be automatically edited to include the current scoreboard</td>
</tr>
<tr>
<td>chat_id</td>
<td>Integer</td>
<td>Optional</td>
<td>Required if <em>inline_message_id</em> is not specified. Unique identifier for the target chat</td>
</tr>
<tr>
<td>message_id</td>
<td>Integer</td>
<td>Optional</td>
<td>Required if <em>inline_message_id</em> is not specified. Identifier of the sent message</td>
</tr>
<tr>
<td>inline_message_id</td>
<td>String</td>
<td>Optional</td>
<td>Required if <em>chat_id</em> and <em>message_id</em> are not specified. Identifier of the inline message</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="getgamehighscores" href="#getgamehighscores"><i class="anchor-icon"></i></a>getGameHighScores</h4>
<p>Use this method to get data for high score tables. Will return the score of the specified user and several of their neighbors in a game. On success, returns an <em>Array</em> of <a href="#gamehighscore">GameHighScore</a> objects.</p>
<blockquote>
<p>This method will currently return scores for the target user, plus two of their closest neighbors on each side. Will also return the top three users if the user and his neighbors are not among them. Please note that this behavior is subject to change.</p>
</blockquote>
<table class="table">
<thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>user_id</td>
<td>Integer</td>
<td>Yes</td>
<td>Target user id</td>
</tr>
<tr>
<td>chat_id</td>
<td>Integer</td>
<td>Optional</td>
<td>Required if <em>inline_message_id</em> is not specified. Unique identifier for the target chat</td>
</tr>
<tr>
<td>message_id</td>
<td>Integer</td>
<td>Optional</td>
<td>Required if <em>inline_message_id</em> is not specified. Identifier of the sent message</td>
</tr>
<tr>
<td>inline_message_id</td>
<td>String</td>
<td>Optional</td>
<td>Required if <em>chat_id</em> and <em>message_id</em> are not specified. Identifier of the inline message</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" name="gamehighscore" href="#gamehighscore"><i class="anchor-icon"></i></a>GameHighScore</h4>
<p>This object represents one row of the high scores table for a game.</p>
<table class="table">
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>position</td>
<td>Integer</td>
<td>Position in high score table for the game</td>
</tr>
<tr>
<td>user</td>
<td><a href="#user">User</a></td>
<td>User</td>
</tr>
<tr>
<td>score</td>
<td>Integer</td>
<td>Score</td>
</tr>
</tbody>
</table>
<hr>
<p>And that&#39;s about all we&#39;ve got for now.<br>If you&#39;ve got any questions, please check out our <a href="/bots/faq"><strong>Bot FAQ »</strong></a></p>
</div>
  
</div>
          
        </div>
      </div>
      <div class="footer_wrap">
  <div class="footer_columns_wrap footer_desktop">
    <div class="footer_column footer_column_telegram">
      <h5>Telegram</h5>
      <div class="footer_telegram_description"></div>
      Telegram – bu xavfsizlik va tezlikka eʼtibor qaratuvchi bulut xizmatlariga asoslangan mobil va ish stoli suhbatlashish ilovasi.
    </div>

    <div class="footer_column">
      <h5><a href="//telegram.org/faq">Haqida</a></h5>
      <ul>
        <li><a href="//telegram.org/faq">Savol-javoblar</a></li>
        <li><a href="//telegram.org/blog">Blog</a></li>
        <li><a href="//telegram.org/jobs">Ish oʻrinlari</a></li>
      </ul>
    </div>
    <div class="footer_column">
      <h5><a href="//telegram.org/apps#mobile-apps">Mobil ilovalar</a></h5>
      <ul>
        <li><a href="//telegram.org/dl/ios">iPhone/iPad</a></li>
        <li><a href="//telegram.org/dl/android">Android</a></li>
        <li><a href="//telegram.org/dl/wp">Windows Phone</a></li>
      </ul>
    </div>
    <div class="footer_column">
      <h5><a href="//telegram.org/apps#desktop-apps">Ish stoli ilovalari</a></h5>
      <ul>
        <li><a href="//desktop.telegram.org/">SHK/Mac/Linux</a></li>
        <li><a href="//macos.telegram.org/">macOS</a></li>
        <li><a href="//telegram.org/dl/web">Veb-brauzer</a></li>
      </ul>
    </div>
    <div class="footer_column footer_column_platform">
      <h5><a href="/">Platforma</a></h5>
      <ul>
        <li><a href="/api">API</a></li>
        <li><a href="//translations.telegram.org/">Tarjimalar</a></li>
        <li><a href="//instantview.telegram.org/">Darhol ochish</a></li>
      </ul>
    </div>
  </div>
  <div class="footer_columns_wrap footer_mobile">
    <div class="footer_column">
      <h5><a href="//telegram.org/faq">Haqida</a></h5>
    </div>
    <div class="footer_column">
      <h5><a href="//telegram.org/blog">Blog</a></h5>
    </div>
    <div class="footer_column">
      <h5><a href="//telegram.org/apps">Ilovalar</a></h5>
    </div>
    <div class="footer_column">
      <h5><a href="/">Platforma</a></h5>
    </div>
    <div class="footer_column">
      <h5><a href="https://twitter.com/telegram" target="_blank" data-track="Follow/Twitter" onclick="trackDlClick(this, event)">Twitter</a></h5>
    </div>
  </div>
</div>
    </div>
    <script src="/js/main.js?43"></script>
    <script src="/js/jquery.min.js?1"></script>
<script src="/js/bootstrap.min.js?1"></script>

    <script>window.initDevPageNav&&initDevPageNav();
backToTopInit("Yuqoriga");
removePreloadInit();
</script>
  </body>
</html>
<!-- page generated in 51.05ms -->
