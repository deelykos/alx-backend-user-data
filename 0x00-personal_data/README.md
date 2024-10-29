# Personal Data

<h2>Resources</h2>

<p><strong>Read or watch:</strong></p>

<ul>
<li><a href="/rltoken/jf71oYqiETchcVhPzQVnyg" title="What Is PII, non-PII, and Personal Data?" target="_blank">What Is PII, non-PII, and Personal Data?</a></li>
<li><a href="/rltoken/W2JiHD6cbJY1scJORyLqnw" title="logging documentation" target="_blank">logging documentation</a></li>
<li><a href="/rltoken/41oaQXfzwnF1i-wT8W0vHw" title="bcrypt package" target="_blank">bcrypt package</a></li>
<li><a href="/rltoken/XCpI9uvguxlTCsAeRCW6SA" title="Logging to Files, Setting Levels, and Formatting" target="_blank">Logging to Files, Setting Levels, and Formatting</a></li>
</ul>

<h2>Learning Objectives</h2>

<p>At the end of this project, you are expected to be able to <a href="/rltoken/yiowzem5NkzxawDmImXy8Q" title="explain to anyone" target="_blank">explain to anyone</a>, <strong>without the help of Google</strong>:</p>

<ul>
<li>Examples of Personally Identifiable Information (PII)</li>
<li>How to implement a log filter that will obfuscate PII fields</li>
<li>How to encrypt a password and check the validity of an input password</li>
<li>How to authenticate to a database using environment variables</li>
</ul>

<h2>Requirements</h2>

<ul>
<li>All your files will be interpreted/compiled on Ubuntu 18.04 LTS using <code>python3</code> (version 3.7)</li>
<li>All your files should end with a new line</li>
<li>The first line of all your files should be exactly <code>#!/usr/bin/env python3</code></li>
<li>A <code>README.md</code> file, at the root of the folder of the project, is mandatory</li>
<li>Your code should use the <code>pycodestyle</code> style (version 2.5)</li>
<li>All your files must be executable</li>
<li>The length of your files will be tested using <code>wc</code></li>
<li>All your modules should have a documentation (<code>python3 -c &#39;print(__import__(&quot;my_module&quot;).__doc__)&#39;</code>)</li>
<li>All your classes should have a documentation (<code>python3 -c &#39;print(__import__(&quot;my_module&quot;).MyClass.__doc__)&#39;</code>)</li>
<li>All your functions (inside and outside a class) should have a documentation (<code>python3 -c &#39;print(__import__(&quot;my_module&quot;).my_function.__doc__)&#39;</code> and <code>python3 -c &#39;print(__import__(&quot;my_module&quot;).MyClass.my_function.__doc__)&#39;</code>)</li>
<li>A documentation is not a simple word, it&rsquo;s a real sentence explaining what&rsquo;s the purpose of the module, class or method (the length of it will be verified)</li>
<li>All your functions should be type annotated</li>
</ul>

  </div>
</div>

This project contains tasks for learning to protect a user's personal data.

## Tasks To Complete

        
          <h2 class="gap">Tasks</h2>

    <div data-role="task11698" data-position="1" id="task-num-0">
      <div class="panel panel-default task-card " id="task-11698">
  <span id="user_id" data-id="34266"></span>

  <div class="panel-heading panel-heading-actions">
    <h3 class="panel-title">
      0. Regex-ing
    </h3>

    <div>
        <span class="label label-info">
          mandatory
        </span>
    </div>
  </div>

  <div class="panel-body">
    <span id="user_id" data-id="34266"></span>

    <!-- Progress vs Score -->
      <div class="task_progress_score_bar truncate" data-task-id="11698" data-correction-id="21820606">
        <div class="task_progress_bar" style="width: 0.0%">
          <div class="task_score_bar" style="width: NaN%">
          </div>
        </div>
        <div class="task_progress_score_text">
          Score: <span class="task_score_value">0.0%</span> (<span class="task_progress_value">Checks completed: 0.0%</span>)
        </div>
      </div>

    <!-- Task Body -->
    <p>Write a function called <code>filter_datum</code> that returns the log message obfuscated: </p>

<ul>
<li>Arguments:

<ul>
<li><code>fields</code>: a list of strings representing all fields to obfuscate</li>
<li><code>redaction</code>: a string representing by what the field will be obfuscated</li>
<li><code>message</code>: a string representing the log line</li>
<li><code>separator</code>: a string representing by which character is separating all fields in the log line (<code>message</code>)</li>
</ul></li>
<li>The function should use a regex to replace occurrences of certain field values.</li>
<li><code>filter_datum</code> should be less than 5 lines long and use <code>re.sub</code> to perform the substitution with a single regex.</li>
</ul>

<pre><code>bob@dylan:~$ cat main.py
#!/usr/bin/env python3
&quot;&quot;&quot;
Main file
&quot;&quot;&quot;

filter_datum = __import__(&#39;filtered_logger&#39;).filter_datum

fields = [&quot;password&quot;, &quot;date_of_birth&quot;]
messages = [&quot;name=egg;email=eggmin@eggsample.com;password=eggcellent;date_of_birth=12/12/1986;&quot;, &quot;name=bob;email=bob@dylan.com;password=bobbycool;date_of_birth=03/04/1993;&quot;]

for message in messages:
    print(filter_datum(fields, &#39;xxx&#39;, message, &#39;;&#39;))

bob@dylan:~$
bob@dylan:~$ ./main.py
name=egg;email=eggmin@eggsample.com;password=xxx;date_of_birth=xxx;
name=bob;email=bob@dylan.com;password=xxx;date_of_birth=xxx;
bob@dylan:~$
</code></pre>

  </div>

  <div class="list-group">
      <!-- LTI Resource -->

    <!-- Task Files -->

    <!-- Task URLs -->

    <!-- Github information -->
      <div class="list-group-item">
        <p><strong>Repo:</strong></p>
        <ul>
          <li>GitHub repository: <code>alx-backend-user-data</code></li>
            <li>Directory: <code>0x00-personal_data</code></li>
            <li>File: <code>filtered_logger.py</code></li>
        </ul>
      </div>

    <!-- Self-paced manual review -->
  </div>

  <!-- Panel footer - Controls -->
  <div class="panel-footer">
      <div class="align-items-center d-flex justify-content-between">
        
<div>
      <button class="btn btn-default btn-sm check-your-task-11698-modal-button" data-task-id="11698" data-toggle="modal" data-target="#task-test-correction-11698-correction-modal" id="task-num-0-check-code-btn" data-gtm-custom-event-name="task_checker_modal" data-gtm-custom-event-options='{&quot;taskId&quot;:11698}'>
          Check submission
      </button>
      <div class="modal fade task_correction_modal student_modal" id="task-test-correction-11698-correction-modal">
    <div class="modal-dialog">
        <div class="modal-content">
            <div class="modal-header">
                <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
                <h4 class="modal-title">Correction of "0. Regex-ing"</h4>
            </div>
            <div class="modal-body">
                <div class="actions">
                    <center>
                        <div class="alert alert-info hidden"></div>

                        <button name="button" type="submit" class="btn btn-primary correction_request_test_send" data-task-id="11698">Start a new test</button>
                        <button class="btn btn-default close-modal hidden" data-dismiss="modal" type="button">Close</button>

                        <div class="spinner" style="display: none;">
                            <div class="bounce1"></div>
                            <div class="bounce2"></div>
                            <div class="bounce3"></div>
                        </div>
                        <div class="error"></div>
                        <div class="info"></div>
                    </center>
                </div>
                <div class="result"></div>

                <div class="help">
    <button data-task-id="11698">
        <i aria-hidden="true" class="fa-solid fa-circle-info "></i>
    </button>
    <div class="help-container" data-task-id="11698">
        <div class="check-line">
            <div class="check-inline requirement success">
                <i aria-hidden="true" class="fa-solid fa-circle-check "></i>
                Requirement success
            </div>
            <div class="check-inline requirement fail">
                <i aria-hidden="true" class="fa-solid fa-circle-xmark "></i>
                Requirement fail
            </div>
        </div>
        <div class="check-line">
            <div class="check-inline code success">
                <i aria-hidden="true" class="fa-solid fa-circle-check "></i>
                Code success
            </div>
            <div class="check-inline code fail">
                <i aria-hidden="true" class="fa-solid fa-circle-xmark "></i>
                Code fail
            </div>
        </div>
        <div class="check-line">
            <div class="check-inline efficiency success">
                <i aria-hidden="true" class="fa-solid fa-circle-check "></i>
                Efficiency success
            </div>
            <div class="check-inline efficiency fail">
                <i aria-hidden="true" class="fa-solid fa-circle-xmark "></i>
                Efficiency fail
            </div>
        </div>
        <div class="check-line">
            <div class="check-inline answer success">
                <i aria-hidden="true" class="fa-solid fa-circle-check "></i>
                Text answer success
            </div>
            <div class="check-inline answer fail">
                <i aria-hidden="true" class="fa-solid fa-circle-xmark "></i>
                Text answer fail
            </div>
        </div>
        <div class="check-line">
            <div class="check-inline requirement fail offline">
                <i aria-hidden="true" class="fa-solid fa-circle-xmark "></i>
                Skipped - Previous check failed
            </div>
        </div>
    </div>
</div>

            </div>
        </div>
    </div>
</div>


      <button class="btn btn-primary btn-sm task_ask_new_correction " data-task-id="11698" data-correction-id="21820606">
        Mark submission
        <span class="in_progress_info">: in progress...</span>
        <span class="error_occurred_info">: an error occurred</span>
      </button>

    <button class="btn btn-default btn-sm" data-toggle="modal" data-target="#container-specs-modal" data-gtm-custom-event-name="task_sandbox_modal" data-gtm-custom-event-options="{&quot;taskId&quot;:11698}"><i aria-hidden="true" class="fa-solid fa-terminal "></i><span>Get a sandbox</span></button>

      <button class="btn btn-default btn-sm" data-task-id="11698" data-toggle="modal" data-target="#task-qa-review-11698-modal" data-gtm-custom-event-name="task_qa_review_modal" data-gtm-custom-event-options='{&quot;taskId&quot;:11698}'>
        View results
      </button>
      <div class="modal fade task_get_qa_review" id="task-qa-review-11698-modal" data-correction-id="21820606" data-task-id="11698">
    <div class="modal-dialog modal-lg">
        <div class="modal-content">
            <div class="modal-header">
                <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
                <h4 class="modal-title">0. Regex-ing</h4>
            </div>
            <div class="modal-body">
                <div class="spinner gap">
                    <div class="bounce1"></div>
                    <div class="bounce2"></div>
                    <div class="bounce3"></div>
                </div>
                <div class="review-container">
                    <div class="review-corrector"></div>
                    <div class="review-github well" style="display:none">
                        <h5>Commit used:</h5>
                        <ul>
                            <li style="display:none"><strong>User:</strong> <code class="review-github-id"></code> <span class="review-github-name">---</span></li>
                            <li style="display:none"><strong>URL:</strong> <a class="review-github-url" target="_blank">Click here</a></li>
                            <li style="display:none"><strong>ID:</strong> <code class="review-github-commit_id">---</code></li>
                            <li style="display:none"><strong>Author:</strong> <span class="review-github-committer_username">---</span></li>
                            <li style="display:none"><strong>Subject:</strong> <em class="review-github-subject">---</em></li>
                            <li style="display:none"><strong>Date:</strong> <span class="review-github-datetime">---</span></li>
                        </ul>
                    </div>
                    <div class="review-percentage_down"></div>
                    <ul class="review-checks list-group sm-gap"></ul>
                    <div class="review-comment"></div>
                </div>
            </div>
        </div>
    </div>
</div>

</div>


        <div class="fs-4">
        </div>
      </div>


  </div>
</div>

    </div>
    <div data-role="task11699" data-position="2" id="task-num-1">
      <div class="panel panel-default task-card " id="task-11699">
  <span id="user_id" data-id="34266"></span>

  <div class="panel-heading panel-heading-actions">
    <h3 class="panel-title">
      1. Log formatter
    </h3>

    <div>
        <span class="label label-info">
          mandatory
        </span>
    </div>
  </div>

  <div class="panel-body">
    <span id="user_id" data-id="34266"></span>

    <!-- Progress vs Score -->
      <div class="task_progress_score_bar truncate" data-task-id="11699" data-correction-id="21820606">
        <div class="task_progress_bar" style="width: 0.0%">
          <div class="task_score_bar" style="width: NaN%">
          </div>
        </div>
        <div class="task_progress_score_text">
          Score: <span class="task_score_value">0.0%</span> (<span class="task_progress_value">Checks completed: 0.0%</span>)
        </div>
      </div>

    <!-- Task Body -->
    <p>Copy the following code into <code>filtered_logger.py</code>.</p>

<pre><code class="python">import logging


class RedactingFormatter(logging.Formatter):
    &quot;&quot;&quot; Redacting Formatter class
        &quot;&quot;&quot;

    REDACTION = &quot;***&quot;
    FORMAT = &quot;[HOLBERTON] %(name)s %(levelname)s %(asctime)-15s: %(message)s&quot;
    SEPARATOR = &quot;;&quot;

    def __init__(self):
        super(RedactingFormatter, self).__init__(self.FORMAT)

    def format(self, record: logging.LogRecord) -&gt; str:
        NotImplementedError
</code></pre>

<p>Update the class to accept a list of strings <code>fields</code> constructor argument.</p>

<p>Implement the <code>format</code> method to filter values in incoming log records using <code>filter_datum</code>. Values for fields in <code>fields</code> should be filtered.</p>

<p>DO NOT extrapolate <code>FORMAT</code> manually. The <code>format</code> method should be less than 5 lines long.</p>

<pre><code>bob@dylan:~$ cat main.py
#!/usr/bin/env python3
&quot;&quot;&quot;
Main file
&quot;&quot;&quot;

import logging
import re

RedactingFormatter = __import__(&#39;filtered_logger&#39;).RedactingFormatter

message = &quot;name=Bob;email=bob@dylan.com;ssn=000-123-0000;password=bobby2019;&quot;
log_record = logging.LogRecord(&quot;my_logger&quot;, logging.INFO, None, None, message, None, None)
formatter = RedactingFormatter(fields=(&quot;email&quot;, &quot;ssn&quot;, &quot;password&quot;))
print(formatter.format(log_record))

bob@dylan:~$
bob@dylan:~$ ./main.py
[HOLBERTON] my_logger INFO 2019-11-19 18:24:25,105: name=Bob; email=***; ssn=***; password=***;
bob@dylan:~$
</code></pre>

  </div>

  <div class="list-group">
      <!-- LTI Resource -->

    <!-- Task Files -->

    <!-- Task URLs -->

    <!-- Github information -->
      <div class="list-group-item">
        <p><strong>Repo:</strong></p>
        <ul>
          <li>GitHub repository: <code>alx-backend-user-data</code></li>
            <li>Directory: <code>0x00-personal_data</code></li>
            <li>File: <code>filtered_logger.py</code></li>
        </ul>
      </div>

    <!-- Self-paced manual review -->
  </div>

  <!-- Panel footer - Controls -->
  <div class="panel-footer">
      <div class="align-items-center d-flex justify-content-between">
        
<div>
      <button class="btn btn-default btn-sm check-your-task-11699-modal-button" data-task-id="11699" data-toggle="modal" data-target="#task-test-correction-11699-correction-modal" id="task-num-1-check-code-btn" data-gtm-custom-event-name="task_checker_modal" data-gtm-custom-event-options='{&quot;taskId&quot;:11699}'>
          Check submission
      </button>
      <div class="modal fade task_correction_modal student_modal" id="task-test-correction-11699-correction-modal">
    <div class="modal-dialog">
        <div class="modal-content">
            <div class="modal-header">
                <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
                <h4 class="modal-title">Correction of "1. Log formatter"</h4>
            </div>
            <div class="modal-body">
                <div class="actions">
                    <center>
                        <div class="alert alert-info hidden"></div>

                        <button name="button" type="submit" class="btn btn-primary correction_request_test_send" data-task-id="11699">Start a new test</button>
                        <button class="btn btn-default close-modal hidden" data-dismiss="modal" type="button">Close</button>

                        <div class="spinner" style="display: none;">
                            <div class="bounce1"></div>
                            <div class="bounce2"></div>
                            <div class="bounce3"></div>
                        </div>
                        <div class="error"></div>
                        <div class="info"></div>
                    </center>
                </div>
                <div class="result"></div>

                <div class="help">
    <button data-task-id="11699">
        <i aria-hidden="true" class="fa-solid fa-circle-info "></i>
    </button>
    <div class="help-container" data-task-id="11699">
        <div class="check-line">
            <div class="check-inline requirement success">
                <i aria-hidden="true" class="fa-solid fa-circle-check "></i>
                Requirement success
            </div>
            <div class="check-inline requirement fail">
                <i aria-hidden="true" class="fa-solid fa-circle-xmark "></i>
                Requirement fail
            </div>
        </div>
        <div class="check-line">
            <div class="check-inline code success">
                <i aria-hidden="true" class="fa-solid fa-circle-check "></i>
                Code success
            </div>
            <div class="check-inline code fail">
                <i aria-hidden="true" class="fa-solid fa-circle-xmark "></i>
                Code fail
            </div>
        </div>
        <div class="check-line">
            <div class="check-inline efficiency success">
                <i aria-hidden="true" class="fa-solid fa-circle-check "></i>
                Efficiency success
            </div>
            <div class="check-inline efficiency fail">
                <i aria-hidden="true" class="fa-solid fa-circle-xmark "></i>
                Efficiency fail
            </div>
        </div>
        <div class="check-line">
            <div class="check-inline answer success">
                <i aria-hidden="true" class="fa-solid fa-circle-check "></i>
                Text answer success
            </div>
            <div class="check-inline answer fail">
                <i aria-hidden="true" class="fa-solid fa-circle-xmark "></i>
                Text answer fail
            </div>
        </div>
        <div class="check-line">
            <div class="check-inline requirement fail offline">
                <i aria-hidden="true" class="fa-solid fa-circle-xmark "></i>
                Skipped - Previous check failed
            </div>
        </div>
    </div>
</div>

            </div>
        </div>
    </div>
</div>


      <button class="btn btn-primary btn-sm task_ask_new_correction " data-task-id="11699" data-correction-id="21820606">
        Mark submission
        <span class="in_progress_info">: in progress...</span>
        <span class="error_occurred_info">: an error occurred</span>
      </button>

    <button class="btn btn-default btn-sm" data-toggle="modal" data-target="#container-specs-modal" data-gtm-custom-event-name="task_sandbox_modal" data-gtm-custom-event-options="{&quot;taskId&quot;:11699}"><i aria-hidden="true" class="fa-solid fa-terminal "></i><span>Get a sandbox</span></button>

      <button class="btn btn-default btn-sm" data-task-id="11699" data-toggle="modal" data-target="#task-qa-review-11699-modal" data-gtm-custom-event-name="task_qa_review_modal" data-gtm-custom-event-options='{&quot;taskId&quot;:11699}'>
        View results
      </button>
      <div class="modal fade task_get_qa_review" id="task-qa-review-11699-modal" data-correction-id="21820606" data-task-id="11699">
    <div class="modal-dialog modal-lg">
        <div class="modal-content">
            <div class="modal-header">
                <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
                <h4 class="modal-title">1. Log formatter</h4>
            </div>
            <div class="modal-body">
                <div class="spinner gap">
                    <div class="bounce1"></div>
                    <div class="bounce2"></div>
                    <div class="bounce3"></div>
                </div>
                <div class="review-container">
                    <div class="review-corrector"></div>
                    <div class="review-github well" style="display:none">
                        <h5>Commit used:</h5>
                        <ul>
                            <li style="display:none"><strong>User:</strong> <code class="review-github-id"></code> <span class="review-github-name">---</span></li>
                            <li style="display:none"><strong>URL:</strong> <a class="review-github-url" target="_blank">Click here</a></li>
                            <li style="display:none"><strong>ID:</strong> <code class="review-github-commit_id">---</code></li>
                            <li style="display:none"><strong>Author:</strong> <span class="review-github-committer_username">---</span></li>
                            <li style="display:none"><strong>Subject:</strong> <em class="review-github-subject">---</em></li>
                            <li style="display:none"><strong>Date:</strong> <span class="review-github-datetime">---</span></li>
                        </ul>
                    </div>
                    <div class="review-percentage_down"></div>
                    <ul class="review-checks list-group sm-gap"></ul>
                    <div class="review-comment"></div>
                </div>
            </div>
        </div>
    </div>
</div>

</div>


        <div class="fs-4">
        </div>
      </div>


  </div>
</div>

    </div>
    <div data-role="task11700" data-position="3" id="task-num-2">
      <div class="panel panel-default task-card " id="task-11700">
  <span id="user_id" data-id="34266"></span>

  <div class="panel-heading panel-heading-actions">
    <h3 class="panel-title">
      2. Create logger
    </h3>

    <div>
        <span class="label label-info">
          mandatory
        </span>
    </div>
  </div>

  <div class="panel-body">
    <span id="user_id" data-id="34266"></span>

    <!-- Progress vs Score -->
      <div class="task_progress_score_bar truncate" data-task-id="11700" data-correction-id="21820606">
        <div class="task_progress_bar" style="width: 0.0%">
          <div class="task_score_bar" style="width: NaN%">
          </div>
        </div>
        <div class="task_progress_score_text">
          Score: <span class="task_score_value">0.0%</span> (<span class="task_progress_value">Checks completed: 0.0%</span>)
        </div>
      </div>

    <!-- Task Body -->
    <p>Use <a href="/rltoken/cVQXXtttuAobcFjYFKZTow" title="user_data.csv" target="_blank">user_data.csv</a> for this task</p>

<p>Implement a <code>get_logger</code> function that takes no arguments and returns a <code>logging.Logger</code> object.</p>

<p>The logger should be named <code>&quot;user_data&quot;</code> and only log up to <code>logging.INFO</code> level. It should not propagate messages to other loggers.
It should have a <code>StreamHandler</code> with <code>RedactingFormatter</code> as formatter.</p>

<p>Create a tuple <code>PII_FIELDS</code> constant at the root of the module containing the fields from <code>user_data.csv</code> that are considered PII. 
<code>PII_FIELDS</code> can contain only 5 fields - choose the right list of fields that can are considered as &ldquo;important&rdquo; PIIs or information that you <strong>must hide</strong> in your logs.
Use it to parameterize the formatter.</p>

<p><strong>Tips:</strong></p>

<ul>
<li><a href="/rltoken/jf71oYqiETchcVhPzQVnyg" title="What Is PII, non-PII, and personal data?" target="_blank">What Is PII, non-PII, and personal data?</a></li>
<li><a href="/rltoken/74q9SbCrKPfvBmpFZnyZxg" title="Uncovering Password Habits" target="_blank">Uncovering Password Habits</a></li>
</ul>

<pre><code>bob@dylan:~$ cat main.py
#!/usr/bin/env python3
&quot;&quot;&quot;
Main file
&quot;&quot;&quot;

import logging

get_logger = __import__(&#39;filtered_logger&#39;).get_logger
PII_FIELDS = __import__(&#39;filtered_logger&#39;).PII_FIELDS

print(get_logger.__annotations__.get(&#39;return&#39;))
print(&quot;PII_FIELDS: {}&quot;.format(len(PII_FIELDS)))

bob@dylan:~$
bob@dylan:~$ ./main.py
&lt;class &#39;logging.Logger&#39;&gt;
PII_FIELDS: 5
bob@dylan:~$
</code></pre>

  </div>

  <div class="list-group">
      <!-- LTI Resource -->

    <!-- Task Files -->

    <!-- Task URLs -->

    <!-- Github information -->
      <div class="list-group-item">
        <p><strong>Repo:</strong></p>
        <ul>
          <li>GitHub repository: <code>alx-backend-user-data</code></li>
            <li>Directory: <code>0x00-personal_data</code></li>
            <li>File: <code>filtered_logger.py</code></li>
        </ul>
      </div>

    <!-- Self-paced manual review -->
  </div>

  <!-- Panel footer - Controls -->
  <div class="panel-footer">
      <div class="align-items-center d-flex justify-content-between">
        
<div>
      <button class="btn btn-default btn-sm check-your-task-11700-modal-button" data-task-id="11700" data-toggle="modal" data-target="#task-test-correction-11700-correction-modal" id="task-num-2-check-code-btn" data-gtm-custom-event-name="task_checker_modal" data-gtm-custom-event-options='{&quot;taskId&quot;:11700}'>
          Check submission
      </button>
      <div class="modal fade task_correction_modal student_modal" id="task-test-correction-11700-correction-modal">
    <div class="modal-dialog">
        <div class="modal-content">
            <div class="modal-header">
                <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
                <h4 class="modal-title">Correction of "2. Create logger"</h4>
            </div>
            <div class="modal-body">
                <div class="actions">
                    <center>
                        <div class="alert alert-info hidden"></div>

                        <button name="button" type="submit" class="btn btn-primary correction_request_test_send" data-task-id="11700">Start a new test</button>
                        <button class="btn btn-default close-modal hidden" data-dismiss="modal" type="button">Close</button>

                        <div class="spinner" style="display: none;">
                            <div class="bounce1"></div>
                            <div class="bounce2"></div>
                            <div class="bounce3"></div>
                        </div>
                        <div class="error"></div>
                        <div class="info"></div>
                    </center>
                </div>
                <div class="result"></div>

                <div class="help">
    <button data-task-id="11700">
        <i aria-hidden="true" class="fa-solid fa-circle-info "></i>
    </button>
    <div class="help-container" data-task-id="11700">
        <div class="check-line">
            <div class="check-inline requirement success">
                <i aria-hidden="true" class="fa-solid fa-circle-check "></i>
                Requirement success
            </div>
            <div class="check-inline requirement fail">
                <i aria-hidden="true" class="fa-solid fa-circle-xmark "></i>
                Requirement fail
            </div>
        </div>
        <div class="check-line">
            <div class="check-inline code success">
                <i aria-hidden="true" class="fa-solid fa-circle-check "></i>
                Code success
            </div>
            <div class="check-inline code fail">
                <i aria-hidden="true" class="fa-solid fa-circle-xmark "></i>
                Code fail
            </div>
        </div>
        <div class="check-line">
            <div class="check-inline efficiency success">
                <i aria-hidden="true" class="fa-solid fa-circle-check "></i>
                Efficiency success
            </div>
            <div class="check-inline efficiency fail">
                <i aria-hidden="true" class="fa-solid fa-circle-xmark "></i>
                Efficiency fail
            </div>
        </div>
        <div class="check-line">
            <div class="check-inline answer success">
                <i aria-hidden="true" class="fa-solid fa-circle-check "></i>
                Text answer success
            </div>
            <div class="check-inline answer fail">
                <i aria-hidden="true" class="fa-solid fa-circle-xmark "></i>
                Text answer fail
            </div>
        </div>
        <div class="check-line">
            <div class="check-inline requirement fail offline">
                <i aria-hidden="true" class="fa-solid fa-circle-xmark "></i>
                Skipped - Previous check failed
            </div>
        </div>
    </div>
</div>

            </div>
        </div>
    </div>
</div>


      <button class="btn btn-primary btn-sm task_ask_new_correction " data-task-id="11700" data-correction-id="21820606">
        Mark submission
        <span class="in_progress_info">: in progress...</span>
        <span class="error_occurred_info">: an error occurred</span>
      </button>

    <button class="btn btn-default btn-sm" data-toggle="modal" data-target="#container-specs-modal" data-gtm-custom-event-name="task_sandbox_modal" data-gtm-custom-event-options="{&quot;taskId&quot;:11700}"><i aria-hidden="true" class="fa-solid fa-terminal "></i><span>Get a sandbox</span></button>

      <button class="btn btn-default btn-sm" data-task-id="11700" data-toggle="modal" data-target="#task-qa-review-11700-modal" data-gtm-custom-event-name="task_qa_review_modal" data-gtm-custom-event-options='{&quot;taskId&quot;:11700}'>
        View results
      </button>
      <div class="modal fade task_get_qa_review" id="task-qa-review-11700-modal" data-correction-id="21820606" data-task-id="11700">
    <div class="modal-dialog modal-lg">
        <div class="modal-content">
            <div class="modal-header">
                <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
                <h4 class="modal-title">2. Create logger</h4>
            </div>
            <div class="modal-body">
                <div class="spinner gap">
                    <div class="bounce1"></div>
                    <div class="bounce2"></div>
                    <div class="bounce3"></div>
                </div>
                <div class="review-container">
                    <div class="review-corrector"></div>
                    <div class="review-github well" style="display:none">
                        <h5>Commit used:</h5>
                        <ul>
                            <li style="display:none"><strong>User:</strong> <code class="review-github-id"></code> <span class="review-github-name">---</span></li>
                            <li style="display:none"><strong>URL:</strong> <a class="review-github-url" target="_blank">Click here</a></li>
                            <li style="display:none"><strong>ID:</strong> <code class="review-github-commit_id">---</code></li>
                            <li style="display:none"><strong>Author:</strong> <span class="review-github-committer_username">---</span></li>
                            <li style="display:none"><strong>Subject:</strong> <em class="review-github-subject">---</em></li>
                            <li style="display:none"><strong>Date:</strong> <span class="review-github-datetime">---</span></li>
                        </ul>
                    </div>
                    <div class="review-percentage_down"></div>
                    <ul class="review-checks list-group sm-gap"></ul>
                    <div class="review-comment"></div>
                </div>
            </div>
        </div>
    </div>
</div>

</div>


        <div class="fs-4">
        </div>
      </div>


  </div>
</div>

    </div>
    <div data-role="task11701" data-position="4" id="task-num-3">
      <div class="panel panel-default task-card " id="task-11701">
  <span id="user_id" data-id="34266"></span>

  <div class="panel-heading panel-heading-actions">
    <h3 class="panel-title">
      3. Connect to secure database
    </h3>

    <div>
        <span class="label label-info">
          mandatory
        </span>
    </div>
  </div>

  <div class="panel-body">
    <span id="user_id" data-id="34266"></span>

    <!-- Progress vs Score -->
      <div class="task_progress_score_bar truncate" data-task-id="11701" data-correction-id="21820606">
        <div class="task_progress_bar" style="width: 0.0%">
          <div class="task_score_bar" style="width: NaN%">
          </div>
        </div>
        <div class="task_progress_score_text">
          Score: <span class="task_score_value">0.0%</span> (<span class="task_progress_value">Checks completed: 0.0%</span>)
        </div>
      </div>

    <!-- Task Body -->
    <p>Database credentials should NEVER be stored in code or checked into version control. One secure option is to store them as environment variable on the application server.</p>

<p>In this task, you will connect to a secure <code>holberton</code> database to read a <code>users</code> table. 
The database is protected by a username and password that are set as environment variables on the server named <code>PERSONAL_DATA_DB_USERNAME</code> (set the default as &ldquo;root&rdquo;), <code>PERSONAL_DATA_DB_PASSWORD</code> (set the default as an empty string) and <code>PERSONAL_DATA_DB_HOST</code> (set the default as &ldquo;localhost&rdquo;). </p>

<p>The database name is stored in <code>PERSONAL_DATA_DB_NAME</code>. </p>

<p>Implement a <code>get_db</code> function that returns a connector to the database (<code>mysql.connector.connection.MySQLConnection</code> object). </p>

<ul>
<li>Use the <code>os</code> module to obtain credentials from the environment</li>
<li>Use the module <code>mysql-connector-python</code> to connect to the MySQL database (<code>pip3 install mysql-connector-python</code>)</li>
</ul>

<pre><code>bob@dylan:~$ cat main.sql
-- setup mysql server
-- configure permissions
CREATE DATABASE IF NOT EXISTS my_db;
CREATE USER IF NOT EXISTS root@localhost IDENTIFIED BY &#39;root&#39;;
GRANT ALL PRIVILEGES ON my_db.* TO &#39;root&#39;@&#39;localhost&#39;;

USE my_db;

DROP TABLE IF EXISTS users;
CREATE TABLE users (
    email VARCHAR(256)
);

INSERT INTO users(email) VALUES (&quot;bob@dylan.com&quot;);
INSERT INTO users(email) VALUES (&quot;bib@dylan.com&quot;);

bob@dylan:~$ 
bob@dylan:~$ cat main.sql | mysql -uroot -p
Enter password: 
bob@dylan:~$ 
bob@dylan:~$ echo &quot;SELECT COUNT(*) FROM users;&quot; | mysql -uroot -p my_db
Enter password: 
2
bob@dylan:~$ 
bob@dylan:~$ cat main.py
#!/usr/bin/env python3
&quot;&quot;&quot;
Main file
&quot;&quot;&quot;

get_db = __import__(&#39;filtered_logger&#39;).get_db

db = get_db()
cursor = db.cursor()
cursor.execute(&quot;SELECT COUNT(*) FROM users;&quot;)
for row in cursor:
    print(row[0])
cursor.close()
db.close()

bob@dylan:~$
bob@dylan:~$ PERSONAL_DATA_DB_USERNAME=root PERSONAL_DATA_DB_PASSWORD=root PERSONAL_DATA_DB_HOST=localhost PERSONAL_DATA_DB_NAME=my_db ./main.py
2
bob@dylan:~$
</code></pre>

  </div>

  <div class="list-group">
      <!-- LTI Resource -->

    <!-- Task Files -->

    <!-- Task URLs -->

    <!-- Github information -->
      <div class="list-group-item">
        <p><strong>Repo:</strong></p>
        <ul>
          <li>GitHub repository: <code>alx-backend-user-data</code></li>
            <li>Directory: <code>0x00-personal_data</code></li>
            <li>File: <code>filtered_logger.py</code></li>
        </ul>
      </div>

    <!-- Self-paced manual review -->
  </div>

  <!-- Panel footer - Controls -->
  <div class="panel-footer">
      <div class="align-items-center d-flex justify-content-between">
        
<div>
      <button class="btn btn-default btn-sm check-your-task-11701-modal-button" data-task-id="11701" data-toggle="modal" data-target="#task-test-correction-11701-correction-modal" id="task-num-3-check-code-btn" data-gtm-custom-event-name="task_checker_modal" data-gtm-custom-event-options='{&quot;taskId&quot;:11701}'>
          Check submission
      </button>
      <div class="modal fade task_correction_modal student_modal" id="task-test-correction-11701-correction-modal">
    <div class="modal-dialog">
        <div class="modal-content">
            <div class="modal-header">
                <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
                <h4 class="modal-title">Correction of "3. Connect to secure database"</h4>
            </div>
            <div class="modal-body">
                <div class="actions">
                    <center>
                        <div class="alert alert-info hidden"></div>

                        <button name="button" type="submit" class="btn btn-primary correction_request_test_send" data-task-id="11701">Start a new test</button>
                        <button class="btn btn-default close-modal hidden" data-dismiss="modal" type="button">Close</button>

                        <div class="spinner" style="display: none;">
                            <div class="bounce1"></div>
                            <div class="bounce2"></div>
                            <div class="bounce3"></div>
                        </div>
                        <div class="error"></div>
                        <div class="info"></div>
                    </center>
                </div>
                <div class="result"></div>

                <div class="help">
    <button data-task-id="11701">
        <i aria-hidden="true" class="fa-solid fa-circle-info "></i>
    </button>
    <div class="help-container" data-task-id="11701">
        <div class="check-line">
            <div class="check-inline requirement success">
                <i aria-hidden="true" class="fa-solid fa-circle-check "></i>
                Requirement success
            </div>
            <div class="check-inline requirement fail">
                <i aria-hidden="true" class="fa-solid fa-circle-xmark "></i>
                Requirement fail
            </div>
        </div>
        <div class="check-line">
            <div class="check-inline code success">
                <i aria-hidden="true" class="fa-solid fa-circle-check "></i>
                Code success
            </div>
            <div class="check-inline code fail">
                <i aria-hidden="true" class="fa-solid fa-circle-xmark "></i>
                Code fail
            </div>
        </div>
        <div class="check-line">
            <div class="check-inline efficiency success">
                <i aria-hidden="true" class="fa-solid fa-circle-check "></i>
                Efficiency success
            </div>
            <div class="check-inline efficiency fail">
                <i aria-hidden="true" class="fa-solid fa-circle-xmark "></i>
                Efficiency fail
            </div>
        </div>
        <div class="check-line">
            <div class="check-inline answer success">
                <i aria-hidden="true" class="fa-solid fa-circle-check "></i>
                Text answer success
            </div>
            <div class="check-inline answer fail">
                <i aria-hidden="true" class="fa-solid fa-circle-xmark "></i>
                Text answer fail
            </div>
        </div>
        <div class="check-line">
            <div class="check-inline requirement fail offline">
                <i aria-hidden="true" class="fa-solid fa-circle-xmark "></i>
                Skipped - Previous check failed
            </div>
        </div>
    </div>
</div>

            </div>
        </div>
    </div>
</div>


      <button class="btn btn-primary btn-sm task_ask_new_correction " data-task-id="11701" data-correction-id="21820606">
        Mark submission
        <span class="in_progress_info">: in progress...</span>
        <span class="error_occurred_info">: an error occurred</span>
      </button>

    <button class="btn btn-default btn-sm" data-toggle="modal" data-target="#container-specs-modal" data-gtm-custom-event-name="task_sandbox_modal" data-gtm-custom-event-options="{&quot;taskId&quot;:11701}"><i aria-hidden="true" class="fa-solid fa-terminal "></i><span>Get a sandbox</span></button>

      <button class="btn btn-default btn-sm" data-task-id="11701" data-toggle="modal" data-target="#task-qa-review-11701-modal" data-gtm-custom-event-name="task_qa_review_modal" data-gtm-custom-event-options='{&quot;taskId&quot;:11701}'>
        View results
      </button>
      <div class="modal fade task_get_qa_review" id="task-qa-review-11701-modal" data-correction-id="21820606" data-task-id="11701">
    <div class="modal-dialog modal-lg">
        <div class="modal-content">
            <div class="modal-header">
                <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
                <h4 class="modal-title">3. Connect to secure database</h4>
            </div>
            <div class="modal-body">
                <div class="spinner gap">
                    <div class="bounce1"></div>
                    <div class="bounce2"></div>
                    <div class="bounce3"></div>
                </div>
                <div class="review-container">
                    <div class="review-corrector"></div>
                    <div class="review-github well" style="display:none">
                        <h5>Commit used:</h5>
                        <ul>
                            <li style="display:none"><strong>User:</strong> <code class="review-github-id"></code> <span class="review-github-name">---</span></li>
                            <li style="display:none"><strong>URL:</strong> <a class="review-github-url" target="_blank">Click here</a></li>
                            <li style="display:none"><strong>ID:</strong> <code class="review-github-commit_id">---</code></li>
                            <li style="display:none"><strong>Author:</strong> <span class="review-github-committer_username">---</span></li>
                            <li style="display:none"><strong>Subject:</strong> <em class="review-github-subject">---</em></li>
                            <li style="display:none"><strong>Date:</strong> <span class="review-github-datetime">---</span></li>
                        </ul>
                    </div>
                    <div class="review-percentage_down"></div>
                    <ul class="review-checks list-group sm-gap"></ul>
                    <div class="review-comment"></div>
                </div>
            </div>
        </div>
    </div>
</div>

</div>


        <div class="fs-4">
        </div>
      </div>


  </div>
</div>

    </div>
    <div data-role="task11702" data-position="5" id="task-num-4">
      <div class="panel panel-default task-card " id="task-11702">
  <span id="user_id" data-id="34266"></span>

  <div class="panel-heading panel-heading-actions">
    <h3 class="panel-title">
      4. Read and filter data
    </h3>

    <div>
        <span class="label label-info">
          mandatory
        </span>
    </div>
  </div>

  <div class="panel-body">
    <span id="user_id" data-id="34266"></span>

    <!-- Progress vs Score -->
      <div class="task_progress_score_bar truncate" data-task-id="11702" data-correction-id="21820606">
        <div class="task_progress_bar" style="width: 100.0%">
          <div class="task_score_bar" style="width: 100.0%">
          </div>
        </div>
        <div class="task_progress_score_text">
          Score: <span class="task_score_value">100.0%</span> (<span class="task_progress_value">Checks completed: 100.0%</span>)
        </div>
      </div>

    <!-- Task Body -->
    <p>Implement a <code>main</code> function that takes no arguments and returns nothing.</p>

<p>The function will obtain a database connection using <code>get_db</code> and retrieve all rows in the <code>users</code> table and display each row under a filtered format like this:</p>

<pre><code class="python">[HOLBERTON] user_data INFO 2019-11-19 18:37:59,596: name=***; email=***; phone=***; ssn=***; password=***; ip=e848:e856:4e0b:a056:54ad:1e98:8110:ce1b; last_login=2019-11-14T06:16:24; user_agent=Mozilla/5.0 (compatible; MSIE 9.0; Windows NT 6.1; WOW64; Trident/5.0; KTXN);
</code></pre>

<p>Filtered fields:</p>

<ul>
<li>name</li>
<li>email</li>
<li>phone</li>
<li>ssn</li>
<li>password</li>
</ul>

<p>Only your <code>main</code> function should run when the module is executed.</p>

<pre><code>bob@dylan:~$ cat main.sql
-- setup mysql server
-- configure permissions
CREATE DATABASE IF NOT EXISTS my_db;
CREATE USER IF NOT EXISTS root@localhost IDENTIFIED BY &#39;root&#39;;
GRANT ALL PRIVILEGES ON my_db.* TO root@localhost;

USE my_db;

DROP TABLE IF EXISTS users;
CREATE TABLE users (
    name VARCHAR(256), 
        email VARCHAR(256), 
        phone VARCHAR(16),
    ssn VARCHAR(16), 
        password VARCHAR(256),
    ip VARCHAR(64), 
        last_login TIMESTAMP,
    user_agent VARCHAR(512)
);

INSERT INTO users(name, email, phone, ssn, password, ip, last_login, user_agent) VALUES (&quot;Marlene Wood&quot;,&quot;hwestiii@att.net&quot;,&quot;(473) 401-4253&quot;,&quot;261-72-6780&quot;,&quot;K5?BMNv&quot;,&quot;60ed:c396:2ff:244:bbd0:9208:26f2:93ea&quot;,&quot;2019-11-14 06:14:24&quot;,&quot;Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/74.0.3729.157 Safari/537.36&quot;);
INSERT INTO users(name, email, phone, ssn, password, ip, last_login, user_agent) VALUES (&quot;Belen Bailey&quot;,&quot;bcevc@yahoo.com&quot;,&quot;(539) 233-4942&quot;,&quot;203-38-5395&quot;,&quot;^3EZ~TkX&quot;,&quot;f724:c5d1:a14d:c4c5:bae2:9457:3769:1969&quot;,&quot;2019-11-14 06:16:19&quot;,&quot;Mozilla/5.0 (Linux; U; Android 4.1.2; de-de; GT-I9100 Build/JZO54K) AppleWebKit/534.30 (KHTML, like Gecko) Version/4.0 Mobile Safari/534.30&quot;);

bob@dylan:~$ 
bob@dylan:~$ cat main.sql | mysql -uroot -p
Enter password: 
bob@dylan:~$ 
bob@dylan:~$ echo &quot;SELECT COUNT(*) FROM users;&quot; | mysql -uroot -p my_db
Enter password: 
2
bob@dylan:~$ 
bob@dylan:~$ PERSONAL_DATA_DB_USERNAME=root PERSONAL_DATA_DB_PASSWORD=root PERSONAL_DATA_DB_HOST=localhost PERSONAL_DATA_DB_NAME=my_db ./filtered_logger.py
[HOLBERTON] user_data INFO 2019-11-19 18:37:59,596: name=***; email=***; phone=***; ssn=***; password=***; ip=60ed:c396:2ff:244:bbd0:9208:26f2:93ea; last_login=2019-11-14 06:14:24; user_agent=Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/74.0.3729.157 Safari/537.36;
[HOLBERTON] user_data INFO 2019-11-19 18:37:59,621: name=***; email=***; phone=***; ssn=***; password=***; ip=f724:c5d1:a14d:c4c5:bae2:9457:3769:1969; last_login=2019-11-14 06:16:19; user_agent=Mozilla/5.0 (Linux; U; Android 4.1.2; de-de; GT-I9100 Build/JZO54K) AppleWebKit/534.30 (KHTML, like Gecko) Version/4.0 Mobile Safari/534.30;
bob@dylan:~$
</code></pre>

  </div>

  <div class="list-group">
      <!-- LTI Resource -->

    <!-- Task Files -->

    <!-- Task URLs -->

    <!-- Github information -->
      <div class="list-group-item">
        <p><strong>Repo:</strong></p>
        <ul>
          <li>GitHub repository: <code>alx-backend-user-data</code></li>
            <li>Directory: <code>0x00-personal_data</code></li>
            <li>File: <code>filtered_logger.py</code></li>
        </ul>
      </div>

    <!-- Self-paced manual review -->
  </div>

  <!-- Panel footer - Controls -->
  <div class="panel-footer">
      <div class="align-items-center d-flex justify-content-between">
        
<div>


    <button class="btn btn-default btn-sm" data-toggle="modal" data-target="#container-specs-modal" data-gtm-custom-event-name="task_sandbox_modal" data-gtm-custom-event-options="{&quot;taskId&quot;:11702}"><i aria-hidden="true" class="fa-solid fa-terminal "></i><span>Get a sandbox</span></button>

      <button class="btn btn-default btn-sm" data-task-id="11702" data-toggle="modal" data-target="#task-qa-review-11702-modal" data-gtm-custom-event-name="task_qa_review_modal" data-gtm-custom-event-options='{&quot;taskId&quot;:11702}'>
        View results
      </button>
      <div class="modal fade task_get_qa_review" id="task-qa-review-11702-modal" data-correction-id="21820606" data-task-id="11702">
    <div class="modal-dialog modal-lg">
        <div class="modal-content">
            <div class="modal-header">
                <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
                <h4 class="modal-title">4. Read and filter data</h4>
            </div>
            <div class="modal-body">
                <div class="spinner gap">
                    <div class="bounce1"></div>
                    <div class="bounce2"></div>
                    <div class="bounce3"></div>
                </div>
                <div class="review-container">
                    <div class="review-corrector"></div>
                    <div class="review-github well" style="display:none">
                        <h5>Commit used:</h5>
                        <ul>
                            <li style="display:none"><strong>User:</strong> <code class="review-github-id"></code> <span class="review-github-name">---</span></li>
                            <li style="display:none"><strong>URL:</strong> <a class="review-github-url" target="_blank">Click here</a></li>
                            <li style="display:none"><strong>ID:</strong> <code class="review-github-commit_id">---</code></li>
                            <li style="display:none"><strong>Author:</strong> <span class="review-github-committer_username">---</span></li>
                            <li style="display:none"><strong>Subject:</strong> <em class="review-github-subject">---</em></li>
                            <li style="display:none"><strong>Date:</strong> <span class="review-github-datetime">---</span></li>
                        </ul>
                    </div>
                    <div class="review-percentage_down"></div>
                    <ul class="review-checks list-group sm-gap"></ul>
                    <div class="review-comment"></div>
                </div>
            </div>
        </div>
    </div>
</div>

</div>


        <div class="fs-4">
        </div>
      </div>


  </div>
</div>

    </div>
    <div data-role="task11703" data-position="6" id="task-num-5">
      <div class="panel panel-default task-card " id="task-11703">
  <span id="user_id" data-id="34266"></span>

  <div class="panel-heading panel-heading-actions">
    <h3 class="panel-title">
      5. Encrypting passwords
    </h3>

    <div>
        <span class="label label-info">
          mandatory
        </span>
    </div>
  </div>

  <div class="panel-body">
    <span id="user_id" data-id="34266"></span>

    <!-- Progress vs Score -->
      <div class="task_progress_score_bar truncate" data-task-id="11703" data-correction-id="21820606">
        <div class="task_progress_bar" style="width: 0.0%">
          <div class="task_score_bar" style="width: NaN%">
          </div>
        </div>
        <div class="task_progress_score_text">
          Score: <span class="task_score_value">0.0%</span> (<span class="task_progress_value">Checks completed: 0.0%</span>)
        </div>
      </div>

    <!-- Task Body -->
    <p>User passwords should NEVER be stored in plain text in a database.</p>

<p>Implement a <code>hash_password</code> function that expects one string argument name <code>password</code> and returns a salted, hashed password, which is a byte string.</p>

<p>Use the <code>bcrypt</code> package to perform the hashing (with <code>hashpw</code>).</p>

<pre><code>bob@dylan:~$ cat main.py
#!/usr/bin/env python3
&quot;&quot;&quot;
Main file
&quot;&quot;&quot;

hash_password = __import__(&#39;encrypt_password&#39;).hash_password

password = &quot;MyAmazingPassw0rd&quot;
print(hash_password(password))
print(hash_password(password))

bob@dylan:~$
bob@dylan:~$ ./main.py
b&#39;$2b$12$Fnjf6ew.oPZtVksngJjh1.vYCnxRjPm2yt18kw6AuprMRpmhJVxJO&#39;
b&#39;$2b$12$xSAw.bxfSTAlIBglPMXeL.SJnzme3Gm0E7eOEKOVV2OhqOakyUN5m&#39;
bob@dylan:~$
</code></pre>

  </div>

  <div class="list-group">
      <!-- LTI Resource -->

    <!-- Task Files -->

    <!-- Task URLs -->

    <!-- Github information -->
      <div class="list-group-item">
        <p><strong>Repo:</strong></p>
        <ul>
          <li>GitHub repository: <code>alx-backend-user-data</code></li>
            <li>Directory: <code>0x00-personal_data</code></li>
            <li>File: <code>encrypt_password.py</code></li>
        </ul>
      </div>

    <!-- Self-paced manual review -->
  </div>

  <!-- Panel footer - Controls -->
  <div class="panel-footer">
      <div class="align-items-center d-flex justify-content-between">
        
<div>
      <button class="btn btn-default btn-sm check-your-task-11703-modal-button" data-task-id="11703" data-toggle="modal" data-target="#task-test-correction-11703-correction-modal" id="task-num-5-check-code-btn" data-gtm-custom-event-name="task_checker_modal" data-gtm-custom-event-options='{&quot;taskId&quot;:11703}'>
          Check submission
      </button>
      <div class="modal fade task_correction_modal student_modal" id="task-test-correction-11703-correction-modal">
    <div class="modal-dialog">
        <div class="modal-content">
            <div class="modal-header">
                <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
                <h4 class="modal-title">Correction of "5. Encrypting passwords"</h4>
            </div>
            <div class="modal-body">
                <div class="actions">
                    <center>
                        <div class="alert alert-info hidden"></div>

                        <button name="button" type="submit" class="btn btn-primary correction_request_test_send" data-task-id="11703">Start a new test</button>
                        <button class="btn btn-default close-modal hidden" data-dismiss="modal" type="button">Close</button>

                        <div class="spinner" style="display: none;">
                            <div class="bounce1"></div>
                            <div class="bounce2"></div>
                            <div class="bounce3"></div>
                        </div>
                        <div class="error"></div>
                        <div class="info"></div>
                    </center>
                </div>
                <div class="result"></div>

                <div class="help">
    <button data-task-id="11703">
        <i aria-hidden="true" class="fa-solid fa-circle-info "></i>
    </button>
    <div class="help-container" data-task-id="11703">
        <div class="check-line">
            <div class="check-inline requirement success">
                <i aria-hidden="true" class="fa-solid fa-circle-check "></i>
                Requirement success
            </div>
            <div class="check-inline requirement fail">
                <i aria-hidden="true" class="fa-solid fa-circle-xmark "></i>
                Requirement fail
            </div>
        </div>
        <div class="check-line">
            <div class="check-inline code success">
                <i aria-hidden="true" class="fa-solid fa-circle-check "></i>
                Code success
            </div>
            <div class="check-inline code fail">
                <i aria-hidden="true" class="fa-solid fa-circle-xmark "></i>
                Code fail
            </div>
        </div>
        <div class="check-line">
            <div class="check-inline efficiency success">
                <i aria-hidden="true" class="fa-solid fa-circle-check "></i>
                Efficiency success
            </div>
            <div class="check-inline efficiency fail">
                <i aria-hidden="true" class="fa-solid fa-circle-xmark "></i>
                Efficiency fail
            </div>
        </div>
        <div class="check-line">
            <div class="check-inline answer success">
                <i aria-hidden="true" class="fa-solid fa-circle-check "></i>
                Text answer success
            </div>
            <div class="check-inline answer fail">
                <i aria-hidden="true" class="fa-solid fa-circle-xmark "></i>
                Text answer fail
            </div>
        </div>
        <div class="check-line">
            <div class="check-inline requirement fail offline">
                <i aria-hidden="true" class="fa-solid fa-circle-xmark "></i>
                Skipped - Previous check failed
            </div>
        </div>
    </div>
</div>

            </div>
        </div>
    </div>
</div>


      <button class="btn btn-primary btn-sm task_ask_new_correction " data-task-id="11703" data-correction-id="21820606">
        Mark submission
        <span class="in_progress_info">: in progress...</span>
        <span class="error_occurred_info">: an error occurred</span>
      </button>

    <button class="btn btn-default btn-sm" data-toggle="modal" data-target="#container-specs-modal" data-gtm-custom-event-name="task_sandbox_modal" data-gtm-custom-event-options="{&quot;taskId&quot;:11703}"><i aria-hidden="true" class="fa-solid fa-terminal "></i><span>Get a sandbox</span></button>

      <button class="btn btn-default btn-sm" data-task-id="11703" data-toggle="modal" data-target="#task-qa-review-11703-modal" data-gtm-custom-event-name="task_qa_review_modal" data-gtm-custom-event-options='{&quot;taskId&quot;:11703}'>
        View results
      </button>
      <div class="modal fade task_get_qa_review" id="task-qa-review-11703-modal" data-correction-id="21820606" data-task-id="11703">
    <div class="modal-dialog modal-lg">
        <div class="modal-content">
            <div class="modal-header">
                <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
                <h4 class="modal-title">5. Encrypting passwords</h4>
            </div>
            <div class="modal-body">
                <div class="spinner gap">
                    <div class="bounce1"></div>
                    <div class="bounce2"></div>
                    <div class="bounce3"></div>
                </div>
                <div class="review-container">
                    <div class="review-corrector"></div>
                    <div class="review-github well" style="display:none">
                        <h5>Commit used:</h5>
                        <ul>
                            <li style="display:none"><strong>User:</strong> <code class="review-github-id"></code> <span class="review-github-name">---</span></li>
                            <li style="display:none"><strong>URL:</strong> <a class="review-github-url" target="_blank">Click here</a></li>
                            <li style="display:none"><strong>ID:</strong> <code class="review-github-commit_id">---</code></li>
                            <li style="display:none"><strong>Author:</strong> <span class="review-github-committer_username">---</span></li>
                            <li style="display:none"><strong>Subject:</strong> <em class="review-github-subject">---</em></li>
                            <li style="display:none"><strong>Date:</strong> <span class="review-github-datetime">---</span></li>
                        </ul>
                    </div>
                    <div class="review-percentage_down"></div>
                    <ul class="review-checks list-group sm-gap"></ul>
                    <div class="review-comment"></div>
                </div>
            </div>
        </div>
    </div>
</div>

</div>


        <div class="fs-4">
        </div>
      </div>


  </div>
</div>

    </div>
    <div data-role="task11704" data-position="7" id="task-num-6">
      <div class="panel panel-default task-card " id="task-11704">
  <span id="user_id" data-id="34266"></span>

  <div class="panel-heading panel-heading-actions">
    <h3 class="panel-title">
      6. Check valid password
    </h3>

    <div>
        <span class="label label-info">
          mandatory
        </span>
    </div>
  </div>

  <div class="panel-body">
    <span id="user_id" data-id="34266"></span>

    <!-- Progress vs Score -->
      <div class="task_progress_score_bar truncate" data-task-id="11704" data-correction-id="21820606">
        <div class="task_progress_bar" style="width: 0.0%">
          <div class="task_score_bar" style="width: NaN%">
          </div>
        </div>
        <div class="task_progress_score_text">
          Score: <span class="task_score_value">0.0%</span> (<span class="task_progress_value">Checks completed: 0.0%</span>)
        </div>
      </div>

    <!-- Task Body -->
    <p>Implement an <code>is_valid</code> function that expects 2 arguments and returns a boolean.</p>

<p>Arguments:</p>

<ul>
<li><code>hashed_password</code>:  <code>bytes</code> type</li>
<li><code>password</code>: string type</li>
</ul>

<p>Use <code>bcrypt</code> to validate that the provided password matches the hashed password.</p>

<pre><code>bob@dylan:~$ cat main.py
#!/usr/bin/env python3
&quot;&quot;&quot;
Main file
&quot;&quot;&quot;

hash_password = __import__(&#39;encrypt_password&#39;).hash_password
is_valid = __import__(&#39;encrypt_password&#39;).is_valid

password = &quot;MyAmazingPassw0rd&quot;
encrypted_password = hash_password(password)
print(encrypted_password)
print(is_valid(encrypted_password, password))

bob@dylan:~$
bob@dylan:~$ ./main.py
b&#39;$2b$12$Fnjf6ew.oPZtVksngJjh1.vYCnxRjPm2yt18kw6AuprMRpmhJVxJO&#39;
True
bob@dylan:~$
</code></pre>

  </div>

  <div class="list-group">
      <!-- LTI Resource -->

    <!-- Task Files -->

    <!-- Task URLs -->

    <!-- Github information -->
      <div class="list-group-item">
        <p><strong>Repo:</strong></p>
        <ul>
          <li>GitHub repository: <code>alx-backend-user-data</code></li>
            <li>Directory: <code>0x00-personal_data</code></li>
            <li>File: <code>encrypt_password.py</code></li>
        </ul>
      </div>

    <!-- Self-paced manual review -->
  </div>

  <!-- Panel footer - Controls -->
  <div class="panel-footer">
      <div class="align-items-center d-flex justify-content-between">
        
<div>
      <button class="btn btn-default btn-sm check-your-task-11704-modal-button" data-task-id="11704" data-toggle="modal" data-target="#task-test-correction-11704-correction-modal" id="task-num-6-check-code-btn" data-gtm-custom-event-name="task_checker_modal" data-gtm-custom-event-options='{&quot;taskId&quot;:11704}'>
          Check submission
      </button>
      <div class="modal fade task_correction_modal student_modal" id="task-test-correction-11704-correction-modal">
    <div class="modal-dialog">
        <div class="modal-content">
            <div class="modal-header">
                <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
                <h4 class="modal-title">Correction of "6. Check valid password"</h4>
            </div>
            <div class="modal-body">
                <div class="actions">
                    <center>
                        <div class="alert alert-info hidden"></div>

                        <button name="button" type="submit" class="btn btn-primary correction_request_test_send" data-task-id="11704">Start a new test</button>
                        <button class="btn btn-default close-modal hidden" data-dismiss="modal" type="button">Close</button>

                        <div class="spinner" style="display: none;">
                            <div class="bounce1"></div>
                            <div class="bounce2"></div>
                            <div class="bounce3"></div>
                        </div>
                        <div class="error"></div>
                        <div class="info"></div>
                    </center>
                </div>
                <div class="result"></div>

                <div class="help">
    <button data-task-id="11704">
        <i aria-hidden="true" class="fa-solid fa-circle-info "></i>
    </button>
    <div class="help-container" data-task-id="11704">
        <div class="check-line">
            <div class="check-inline requirement success">
                <i aria-hidden="true" class="fa-solid fa-circle-check "></i>
                Requirement success
            </div>
            <div class="check-inline requirement fail">
                <i aria-hidden="true" class="fa-solid fa-circle-xmark "></i>
                Requirement fail
            </div>
        </div>
        <div class="check-line">
            <div class="check-inline code success">
                <i aria-hidden="true" class="fa-solid fa-circle-check "></i>
                Code success
            </div>
            <div class="check-inline code fail">
                <i aria-hidden="true" class="fa-solid fa-circle-xmark "></i>
                Code fail
            </div>
        </div>
        <div class="check-line">
            <div class="check-inline efficiency success">
                <i aria-hidden="true" class="fa-solid fa-circle-check "></i>
                Efficiency success
            </div>
            <div class="check-inline efficiency fail">
                <i aria-hidden="true" class="fa-solid fa-circle-xmark "></i>
                Efficiency fail
            </div>
        </div>
        <div class="check-line">
            <div class="check-inline answer success">
                <i aria-hidden="true" class="fa-solid fa-circle-check "></i>
                Text answer success
            </div>
            <div class="check-inline answer fail">
                <i aria-hidden="true" class="fa-solid fa-circle-xmark "></i>
                Text answer fail
            </div>
        </div>
        <div class="check-line">
            <div class="check-inline requirement fail offline">
                <i aria-hidden="true" class="fa-solid fa-circle-xmark "></i>
                Skipped - Previous check failed
            </div>
        </div>
    </div>
</div>

            </div>
        </div>
    </div>
</div>


      <button class="btn btn-primary btn-sm task_ask_new_correction " data-task-id="11704" data-correction-id="21820606">
        Mark submission
        <span class="in_progress_info">: in progress...</span>
        <span class="error_occurred_info">: an error occurred</span>
      </button>

    <button class="btn btn-default btn-sm" data-toggle="modal" data-target="#container-specs-modal" data-gtm-custom-event-name="task_sandbox_modal" data-gtm-custom-event-options="{&quot;taskId&quot;:11704}"><i aria-hidden="true" class="fa-solid fa-terminal "></i><span>Get a sandbox</span></button>

      <button class="btn btn-default btn-sm" data-task-id="11704" data-toggle="modal" data-target="#task-qa-review-11704-modal" data-gtm-custom-event-name="task_qa_review_modal" data-gtm-custom-event-options='{&quot;taskId&quot;:11704}'>
        View results
      </button>
      <div class="modal fade task_get_qa_review" id="task-qa-review-11704-modal" data-correction-id="21820606" data-task-id="11704">
    <div class="modal-dialog modal-lg">
        <div class="modal-content">
            <div class="modal-header">
                <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
                <h4 class="modal-title">6. Check valid password</h4>
            </div>
            <div class="modal-body">
                <div class="spinner gap">
                    <div class="bounce1"></div>
                    <div class="bounce2"></div>
                    <div class="bounce3"></div>
                </div>
                <div class="review-container">
                    <div class="review-corrector"></div>
                    <div class="review-github well" style="display:none">
                        <h5>Commit used:</h5>
                        <ul>
                            <li style="display:none"><strong>User:</strong> <code class="review-github-id"></code> <span class="review-github-name">---</span></li>
                            <li style="display:none"><strong>URL:</strong> <a class="review-github-url" target="_blank">Click here</a></li>
                            <li style="display:none"><strong>ID:</strong> <code class="review-github-commit_id">---</code></li>
                            <li style="display:none"><strong>Author:</strong> <span class="review-github-committer_username">---</span></li>
                            <li style="display:none"><strong>Subject:</strong> <em class="review-github-subject">---</em></li>
                            <li style="display:none"><strong>Date:</strong> <span class="review-github-datetime">---</span></li>
                        </ul>
                    </div>
                    <div class="review-percentage_down"></div>
                    <ul class="review-checks list-group sm-gap"></ul>
                    <div class="review-comment"></div>
                </div>
            </div>
        </div>
    </div>
</div>

</div>


        <div class="fs-4">
        </div>
      </div>


  </div>
</div>

    </div>



            <div data-react-class="projects/ProjectReadyForReview" data-react-props="{&quot;csrfToken&quot;:&quot;38cUE1GexvJ79Mfer1gryV-jzxY55rPIxKtQ3m0vwRVDI0eQaT-dYsZvhQEZUHpkap_fACeImMC9hrUgJvbXEQ&quot;,&quot;firstReview&quot;:false,&quot;peerReview&quot;:{&quot;availableReviewersURI&quot;:&quot;/corrections/21820606/available_reviewers.json&quot;,&quot;canReviewPeerDirectly&quot;:true,&quot;cancelReadyForReviewURI&quot;:&quot;/corrections/21820606/cancel_ready_for_review.json&quot;,&quot;closeAt&quot;:&quot;2024-02-11T05:00:00.000Z&quot;,&quot;correctCorrectionURI&quot;:&quot;https://intranet.alxswe.com/corrections/21820606/correct&quot;,&quot;disabled&quot;:false,&quot;manualReviewBehavior&quot;:&quot;any_student&quot;,&quot;openAt&quot;:&quot;2024-02-07T05:00:00.000Z&quot;,&quot;qaReviewsURI&quot;:&quot;/corrections/to_review&quot;,&quot;readyForReviewURI&quot;:&quot;/corrections/21820606/toggle_ready_for_review.json&quot;,&quot;synchronousManualReview&quot;:false},&quot;toggled&quot;:false}" data-react-cache-id="projects/ProjectReadyForReview-0"></div>

          <div class="modal fade" id="container-specs-modal"><div class="modal-dialog modal-lg"><div class="modal-content"><div class="modal-header"><button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button><h4 class="modal-title">Recommended Sandbox</h4></div><div class="modal-body"><div data-react-class="user_containers/ContainerSpecs" data-react-props="{&quot;containerModelName&quot;:&quot;Sandbox&quot;,&quot;containerSpecs&quot;:[{&quot;available&quot;:true,&quot;description&quot;:&quot;\u003cp\u003eUbuntu 18.04 with Python 3.7\u003c/p\u003e\n&quot;,&quot;id&quot;:23,&quot;name&quot;:&quot;Ubuntu 18.04 - Python 3.7&quot;,&quot;online&quot;:true}],&quot;containersLimit&quot;:2,&quot;csrfToken&quot;:&quot;B_EAquWj9w11LkisTdpCaMnSLt19n2L8KCGI_ZboAMGbFVMp3QKsnci1CnP70hPF_O4-y2PxSfRRDG0D3TEWxQ&quot;,&quot;startStatusURI&quot;:&quot;/user_containers/start_status.json&quot;,&quot;startURI&quot;:&quot;/user_containers/start.json&quot;}" data-react-cache-id="user_containers/ContainerSpecs-0"></div></div></div></div></div>

  </div>
</div>


      
    </div>
  </div>


      </article>

        <div class="copyright">Copyright © 2024 ALX, All rights reserved.</div>

    </main>

        <button class="btn btn-primary atop-help" id="search-button" data-search-active="false" data-toggle="modal" data-target="#search-modal">
  <i aria-hidden="true" class="fa-solid fa-magnifying-glass "></i>
  <i aria-hidden="true" class="fa-solid fa-window-minimize "></i>
</button>

        <div class="modal fade" id="search-modal" tabindex="-1" role="dialog" aria-labelledby="search-modal-label">
    <div class="modal-dialog modal-md">
        <div class="modal-content">
            <div class="modal-header">
                <div id="search-bar-container">
    <input id="search-bar"
            autocomplete="off"
            type="text"
            name="hbtn-search-bar"
            placeholder="✨Start search by typing in this field✨">
</div>

            </div>
            <div class="modal-body">
                <div id="modal-spinner" class="spinner gap">
                    <div class="bounce1"></div>
                    <div class="bounce2"></div>
                    <div class="bounce3"></div>
                </div>
                <div id="search-results-container">
</div>

            </div>
        </div>
    </div>
</div>



        <div class="modal fade" id="markdownGuideModal" tabindex="-1" role="dialog" aria-labelledby="markdownGuideModalLabel" aria-hidden="true">
  <div class="modal-dialog modal-md">
    <div class="modal-content">
        <div class="modal-header">
          <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
          <h4 class="modal-title">Markdown Guide</h4>
        </div>
        <div class="modal-body">
            <h4>Emphasis</h4>
<pre>**<strong>bold</strong>**
*<em>italics</em>*
~~<strike>strikethrough</strike>~~</pre>
<h4>Headers</h4>
<pre># Big header
## Medium header
### Small header
#### Tiny header</pre>
<h4>Lists</h4>
<pre>* Generic list item
* Generic list item
* Generic list item

1. Numbered list item
2. Numbered list item
3. Numbered list item</pre>
<h4>Links</h4>
<pre>[Text to display](http://www.example.com)</pre>
<h4>Quotes</h4>
<pre>> This is a quote.
> It can span multiple lines!</pre>
<h4>Images</h4>
<p>CSS style available: <code>width, height, opacity</code></p>
<pre>![](http://www.example.com/image.jpg)
![](http://www.example.com/image.jpg | width: 200px)
![](http://www.example.com/image.jpg | height: 124px | width: 80px | opacity: 0.6)
</pre>
<h4>Tables</h4>
<pre>| Column 1 | Column 2 | Column 3 |
| -------- | -------- | -------- |
| John     | Doe      | Male     |
| Mary     | Smith    | Female   |

<em>Or without aligning the columns...</em>

| Column 1 | Column 2 | Column 3 |
| -------- | -------- | -------- |
| John | Doe | Male |
| Mary | Smith | Female |
</pre>
<h4>Displaying code</h4>
<pre>`var example = "hello!";`

<em>Or spanning multiple lines...</em>

```
var example = "hello!";
alert(example);
```</pre>
        </div>
    </div>
  </div>
</div>
