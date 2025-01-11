---
layout: default
title: Dataset
nav_order: 2
description: "Mobile Application Coverage: The 25% Curse and Ways Forward"
permalink: /docs/dataset
---



<script type="text/javascript">
        function showHideRow(row) {
            $("#" + row).toggle();
        }
</script>

<style>
    .table_dataset .hidden_info {
        display: none;
    }
    .table_dataset {
        border-collapse: collapse;
    }
    .table_dataset tr.app_short:hover td {
        background-color: #E6E6FA;
    }
</style>

<div style="text-align: left"> 
    All information provided below about the dataset can be downloaded as an <a href="assets/data/BenchInfo.xlsx">excel file</a>.
</div>


---

### Selected Google Play Applications

<!-- Here put a list of all the applications and on click show the detailed info from the table, should be loaded from excel !-->

We select 42 top ranked free applications from the Google Play Store, sampled in 2023, covering all app categories:

<table id="table_topgp" class="table_dataset">
    <thead>
        <tr>
            <th style="text-align: left"> Application</th>
            <th style="text-align: left"> Package Name</th>
            <th style="text-align: left"> Version</th>
            <!--th style="text-align: left"> Category</th>
            <th style="text-align: left"> Downloads</th>
            <th style="text-align: left"> Popularity</th-->
        </tr>
    </thead>
    <tbody>
    {% for value in site.data.topgp-info %}
    {% assign tr_id = 'hidden_info_gp' | append: forloop.index %}
    {% assign onClickFunc = "showHideRow('" | append: tr_id | append: "')" %}
    <tr onClick="{{ onClickFunc }}" class="app_short">
        <td style="text-align: left"> {{ value.application_name }}</td>
        <td style="text-align: left"> {{ value.package_name }}</td>
        <td style="text-align: left"> {{ value.version }}</td>
    </tr>
    <tr id= {{ tr_id }} class="hidden_info">
    <!--td></td-->
    <td colspan="3">
        <table>
            <thead>
                <tr>
                <th style="text-align: left"> Category</th>
                <!--th style="text-align: left"> Downloads</th>
                <th style="text-align: left"> Popularity</th-->
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td style="text-align: left"> {{ value.category }}</td>
                </tr>
                <thead>
                    <th style="text-align: left"> # Activities</th>
                </thead>
                <tr>
                    <td style="text-align: left"> {{ value.activities }}</td>
                    <!--td style="text-align: left"> {{ value.popularity_rank }}</td-->
                </tr>
                <thead>
                    <tr>
                        <th style="text-align: left"> Downloads</th>
                    </tr>
                </thead>
                <tr>
                    <td style="text-align: left"> {{ value.downloads }}</td>
                </tr>
                <thead>
                    <tr>
                        <th style="text-align: left"> Popularity</th>
                    </tr>
                </thead>
                <tr>
                    <td style="text-align: left"> {{ value.popularity_rank }}</td>
                </tr>
                 <thead>
                    <tr>
                        <th style="text-align: left"> Minimum SDK</th>
                    </tr>
                </thead>
                <tr>
                    <td style="text-align: left"> {{ value.min_sdk }}</td>
                </tr>
                <thead>
                    <tr>
                        <th style="text-align: left"> Target SDK</th>
                    </tr>
                </thead>
                <tr>
                    <td style="text-align: left"> {{ value.target_sdk }}</td>
                </tr>
                <thead>
                    <tr>
                    <th style="text-align: left"> # Permissions (in Manifest)</th>
                    </tr>
                </thead>
                {% assign permissions = value.permissions | split: "; " %}
                <tr>
                    <td style="text-align: left"> {{ value.num_permissions }}</td>
                </tr>
                <thead>
                    <tr>
                        <th style="text-align: left"> List of permissions (in Manifest)</th>
                    </tr>
                </thead>
                <tr>
                    <td style="text-align: left"> 
                    {% for permission in permissions %}
                        <tr> <td>{{ permission }}</td></tr>
                    {% endfor %}
                    </td>
                </tr>
                <thead>
                    <tr>
                    <th style="text-align: left"> # Features (in Manifest)</th>
                    </tr>
                </thead>
                {% assign features = value.features | split: "; " %}
                <tr>
                    <td style="text-align: left"> {{ value.num_features }}</td>
                </tr>
                <thead>
                    <tr>
                        <th style="text-align: left"> List of features (in Manifest)</th>
                    </tr>
                </thead>
                <tr>
                    <td style="text-align: left"> 
                    {% for feature in features %}
                        <tr> <td>{{ feature | split: "implied" | first}}</td></tr>
                    {% endfor %}
                    </td>
                </tr>
            </tbody>
        </table>
    </td>
    <!--td colspan="2">
        <table>
            <thead>
                <tr>
                <th style="text-align: left"> Downloads</th>
                <th style="text-align: left"> Popularity</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td style="text-align: left"> {{ value.downloads }}</td>
                    <td style="text-align: left"> {{ value.popularity_rank }}</td>
                </tr>
            </tbody>
        </table>
        </td-->
    </tr>
    {% endfor %}
    </tbody>
</table>

<!--a href="../assets/images/apps-latest.png">
    <img 
        src="../assets/images/apps-latest.png"
        alt="Selected Google Play Applications"
    >
</a-->

---

### Selected Benchmark Applications
<a hr>

We also experiment on a subset applications from the [AndroTest dataset](http://www.cc.gatech.edu/∼orso/software/androtest). From 68 applications originally present in the dataset, we exclude 7 apps which crash on startup and for which we can not reliably identify source code.

We reconstitute the dataset by selecting the latest available version for each of the 61 applications as of 2023.
We further divide it into two datasets depending on whether the applications are also available on the Google Play Store or not, namely BenchGP:

<table id="table_bgp" class="table_dataset">
    <thead>
        <tr>
            <th style="text-align: left"> Application</th>
            <th style="text-align: left"> Package Name</th>
            <th style="text-align: left"> Version</th>
        </tr>
    </thead>
    <tbody>
    {% for value in site.data.benchgp-info %}
    {% assign tr_id = 'hidden_info_bgp' | append: forloop.index %}
    {% assign onClickFunc = "showHideRow('" | append: tr_id | append: "')" %}
    <tr onClick="{{ onClickFunc }}" class="app_short">
        <td style="text-align: left"> {{ value.application_name }}</td>
        <td style="text-align: left"> {{ value.package_name }}</td>
        <td style="text-align: left"> {{ value.current_version }}</td>
    </tr>
    <tr id= {{ tr_id }} class="hidden_info">
    <!--td></td-->
    <td colspan="3">
        <table>
            <thead>
                <tr>
                <th style="text-align: left"> Original Version</th>
                <!--th style="text-align: left"> Downloads</th>
                <th style="text-align: left"> Popularity</th-->
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td style="text-align: left"> {{ value.original_version }}</td>
                </tr>
                <thead>
                    <th style="text-align: left">Year</th>
                </thead>
                <tr>
                    <td style="text-align: left"> {{ value.year }}</td>
                    <!--td style="text-align: left"> {{ value.popularity_rank }}</td-->
                </tr>
                <thead>
                    <tr>
                        <th style="text-align: left"> Source</th>
                    </tr>
                </thead>
                <tr>
                    <td style="text-align: left"> {{ value.source }}</td>
                </tr>
                <thead>
                    <tr>
                        <th style="text-align: left"> # Activities</th>
                    </tr>
                </thead>
                <tr>
                    <td style="text-align: left"> {{ value.activities }}</td>
                </tr>
                 <thead>
                    <tr>
                        <th style="text-align: left"> Minimum SDK</th>
                    </tr>
                </thead>
                <tr>
                    <td style="text-align: left"> {{ value.min_sdk }}</td>
                </tr>
                <thead>
                    <tr>
                        <th style="text-align: left"> Target SDK</th>
                    </tr>
                </thead>
                <tr>
                    <td style="text-align: left"> {{ value.target_sdk }}</td>
                </tr>
                <thead>
                    <tr>
                    <th style="text-align: left"> # Permissions (in Manifest)</th>
                    </tr>
                </thead>
                {% assign permissions = value.permissions | split: "; " %}
                <tr>
                    <td style="text-align: left"> {{ value.num_permissions }}</td>
                </tr>
                <thead>
                    <tr>
                        <th style="text-align: left"> List of permissions (in Manifest)</th>
                    </tr>
                </thead>
                <tr>
                    <td style="text-align: left"> 
                    {% for permission in permissions %}
                        <tr> <td>{{ permission }}</td></tr>
                    {% endfor %}
                    </td>
                </tr>
                <thead>
                    <tr>
                    <th style="text-align: left"> # Features (in Manifest)</th>
                    </tr>
                </thead>
                {% assign features = value.features | split: "; " %}
                <tr>
                    <td style="text-align: left"> {{ value.num_features }}</td>
                </tr>
                <thead>
                    <tr>
                        <th style="text-align: left"> List of features (in Manifest)</th>
                    </tr>
                </thead>
                <tr>
                    <td style="text-align: left"> 
                    {% for feature in features %}
                        <tr> <td>{{ feature | split: "implied" | first}}</td></tr>
                    {% endfor %}
                    </td>
                </tr>
            </tbody>
        </table>
    </td>
    </tr>
    {% endfor %}
    </tbody>
</table>

and BenchNotGP:
<table id="table_bgp" class="table_dataset">
    <thead>
        <tr>
            <th style="text-align: left"> Application</th>
            <th style="text-align: left"> Package Name</th>
            <th style="text-align: left"> Version</th>
        </tr>
    </thead>
    <tbody>
    {% for value in site.data.benchnotgp-info %}
    {% assign tr_id = 'hidden_info_bngp' | append: forloop.index %}
    {% assign onClickFunc = "showHideRow('" | append: tr_id | append: "')" %}
    <tr onClick="{{ onClickFunc }}" class="app_short">
        <td style="text-align: left"> {{ value.application_name }}</td>
        <td style="text-align: left"> {{ value.package_name }}</td>
        <td style="text-align: left"> {{ value.current_version }}</td>
    </tr>
    <tr id= {{ tr_id }} class="hidden_info">
    <!--td></td-->
    <td colspan="3">
        <table>
            <thead>
                <tr>
                <th style="text-align: left"> Original Version</th>
                <!--th style="text-align: left"> Downloads</th>
                <th style="text-align: left"> Popularity</th-->
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td style="text-align: left"> {{ value.original_version }}</td>
                </tr>
                <thead>
                    <th style="text-align: left">Year</th>
                </thead>
                <tr>
                    <td style="text-align: left"> {{ value.year }}</td>
                    <!--td style="text-align: left"> {{ value.popularity_rank }}</td-->
                </tr>
                <thead>
                    <tr>
                        <th style="text-align: left"> Source</th>
                    </tr>
                </thead>
                <tr>
                    <td style="text-align: left"> {{ value.source }}</td>
                </tr>
                <thead>
                    <tr>
                        <th style="text-align: left"> # Activities</th>
                    </tr>
                </thead>
                <tr>
                    <td style="text-align: left"> {{ value.activities }}</td>
                </tr>
                 <thead>
                    <tr>
                        <th style="text-align: left"> Minimum SDK</th>
                    </tr>
                </thead>
                <tr>
                    <td style="text-align: left"> {{ value.min_sdk }}</td>
                </tr>
                <thead>
                    <tr>
                        <th style="text-align: left"> Target SDK</th>
                    </tr>
                </thead>
                <tr>
                    <td style="text-align: left"> {{ value.target_sdk }}</td>
                </tr>
                <thead>
                    <tr>
                    <th style="text-align: left"> # Permissions (in Manifest)</th>
                    </tr>
                </thead>
                {% assign permissions = value.permissions | split: "; " %}
                <tr>
                    <td style="text-align: left"> {{ value.num_permissions }}</td>
                </tr>
                <thead>
                    <tr>
                        <th style="text-align: left"> List of permissions (in Manifest)</th>
                    </tr>
                </thead>
                <tr>
                    <td style="text-align: left"> 
                    {% for permission in permissions %}
                        <tr> <td>{{ permission }}</td></tr>
                    {% endfor %}
                    </td>
                </tr>
                <thead>
                    <tr>
                    <th style="text-align: left"> # Features (in Manifest)</th>
                    </tr>
                </thead>
                {% assign features = value.features | split: "; " %}
                <tr>
                    <td style="text-align: left"> {{ value.num_features }}</td>
                </tr>
                <thead>
                    <tr>
                        <th style="text-align: left"> List of features (in Manifest)</th>
                    </tr>
                </thead>
                <tr>
                    <td style="text-align: left"> 
                    {% for feature in features %}
                        <tr> <td>{{ feature | split: "implied" | first}}</td></tr>
                    {% endfor %}
                    </td>
                </tr>
            </tbody>
        </table>
    </td>
    </tr>
    {% endfor %}
    </tbody>
</table>



<!--a href="../assets/images/benchgp.png">
    <img 
        src="../assets/images/benchgp.png"
        alt="Selected Benchmark Applications (on Google Play)"
    >
</a>

<a href="../assets/images/benchnotgp.png">
    <img 
        src="../assets/images/benchnotgp.png"
        alt="Selected Benchmark Applications (not on Google Play)"
    >
</a-->

<!--We provide additional details about the selected applications namely the application size, targeted SDK version and used permissions in this [excel file](assets/data/BenchInfo.xlsx).-->