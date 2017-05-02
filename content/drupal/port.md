+++
draft = false
title = "Drupal 8 Port"
description="Port for Drupal @ Open Data."
language = "en"
tags = [
    "drupal",
    "roadmap"
]
date = "2017-01-01T13:10:52-05:00"
type = "single"
+++

## Background

This section highlights the progress being made related to the porting of the
legacy `Open Data` platform from `Drupal 7` to `Drupal 8`. During the port the
primary focus is on ensuring there is no loss of any content / user / comments
and on simplifying the data model for a few of the more complicated
functionalities provided in the legacy site.

## Overview

This section while not exhaustive attempts to provide a breakdown of the bulk
of the work being done while porting the legacy site to `Drupal 8`.
Unfortunately given the sheer number of features the `Open Data` platform
supports this section will exclusively focus on business crucial functionality
and will be updated continuously as work progresses.

> <strong>Note</strong>: To see specific information about the various features
we provide please consult the <a href="{{< relref "drupal/service/webform.md" >}}">
Services</a> page.

<table id="components-theme" class="wb-tables table table-striped table-hover" data-wb-tables='{"columnDefs": [ { "visible": true, "targets": [ 3 ] } ], "lengthMenu": [[10, 25, -1], [10, 25, "All"]], "pageLength": 10 }'>
    <thead>
        <tr>
            <th>Priority #</th>
            <th>Feature</th>
            <th>Status</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr class="success">
            <td>1</td>
            <td>GCWeb theme</td>
            <td>Ported</td>
            <td>
                <p>The GCWeb theme has been ported along with all of the other themes</p>
                <p>The GCWeb layouts have been imported / can be leveraged through UI @<code  class="text-danger">bootstrap_layouts</code></p>
            </td>
        </tr>
        <tr class="success">
            <td>2</td>
            <td>Install Profile</td>
            <td>Ported</td>
            <td>
                <p>Created new <a href="http://github.com/open-data/od">Open
                Data</a> install profile that can be leveraged for new projects
                </p>
                <p>Exported all relevant configuration and system settings</p>
            </td>
        </tr>
        <tr class="success">
            <td>3</td>
            <td>Migration</td>
            <td>Ported</td>
            <td>
                <p>All entities (<code>comments</code>, <code>nodes</code>,
                <code>webforms</code>, <code>user</code>, <code>terms</code>,
                etc) have been migrated</p>
                <p>All file system media have been migrated</p>
                <p>Most logic contained in:
                    <ul>
                        <li><a href="https://github.com/open-data/od/tree/8.x-2.x/modules/custom/od_ext/od_ext_migration">Open Data Extend: Migrate</a>
                        </li>
                    </ul>
                </p>
            </td>
        </tr>
        <tr class="success">
            <td>4</td>
            <td>Commenting / Rating</td>
            <td>Ported</td>
            <td>
                <p>This is being completely handled largely through
                <code>REST</code></p>
                <p>Ability to connect to datasets from external db's and
                leverage as if they were native in <code>Drupal 8</code></p>
                <p>Content lives externally, but Drupal sees those remote
                entities as internal<p>
                <p>Largely functionality accomplished through:
                    <ul>
                        <li><a href="http://drupal.org/project/external_entities">External Entities</a></li>
                        <li><a href="http://github.com/open-data/external_comment">External Comment</a</li>
                        <li><a href="https://github.com/open-data/od/tree/8.x-2.x/modules/custom/od_ext/od_ext_services">Open Data Extend: Services</a</li>
                    </ul>
                </p>
            </td>
        </tr>
        <tr class="success">
            <td>5</td>
            <td>Search Pages / Proactive Disclosure</td>
            <td>Ported</td>
            <td>
                <p>All search pages are now panelized landing pages</p>
                <p>Each search page is now completely revisionable and deployable</p>
                <p>Simplified the workflow for creating a search page along
                with a helpful wizard</p>
                <p>Largely functionality accomplished through:
                    <ul>
                        <li><a href="http://drupal.org/project/search_api">Search API</a></li>
                        <li><a href="http://drupal.org/project/search_api_solr">Search API Solr</a</li>
                        <li><a href="https://github.com/sylus/search_api_solr_datasource">Search API Solr External Datasource</a</li>
                        <li><a href="https://github.com/open-data/od/tree/8.x-2.x/modules/custom/od_solr/">Open Data: Solr</a</li>
                    </ul>
                </p>
            </td>
        </tr>
        <tr class="success">
            <td>6</td>
            <td>Analytics / D3</td>
            <td>New</td>
            <td>
                <p>Provide integration with google analytics and collect reports</p>
                <p>Provide different reports along with corresponding visualization leveraging D3.js</p>
                <p>Largely functionality accomplished through:
                    <ul>
                        <li><a href="http://drupal.org/project/google_analytics_reports">
                        Google Analytics Reports</a></li>
                        <li><a href="https://github.com/open-data/od/tree/8.x-2.x/modules/custom/od_ext/od_ext_analytics">Open Data Extend: Analytics</a</li>
                    </ul>
                </p>
            </td>
        </tr>
        <tr class="success">
            <td>7</td>
            <td>Testing</td>
            <td>New</td>
            <td>
                <p>Ported all relevant Drupal 7 behat tests</p>
                <p>Added a variety of additional Kernel + Unit tests for
                PHPUnit</p>
                <p>Roughly double the amount of behat tests added for Drupal 8</p>
            </td>
        </tr>
    </tbody>
</table>
