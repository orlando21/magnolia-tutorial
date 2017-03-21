---
layout: post
title: Managing a campaign with the Campaign Manager App
tags: [tutorial, easy]
---

In this tutorial you learn how to manage an online campaign using the Campaign Manager App. You will create the campaign and associate with content on your site. You will also make the campaign go live by reviewing it and publishing the associated content.

- [Prerequisites](#prerequisites)
- [Create the campaign](#create)
- [Add the campaign to a page](#campaign)
- [Add an image to the campaign](#image)
- [Add a template to the campaign](#template)
- [Add a resource to the campaign](#resource)
- [Add a content node to the campaign](#node)
- [Reviewing content in the campaign](#review)
- [Publishing the content](#publish)
- [Further reading](#reading)

### Prerequisites<a name="prerequisites"></a>

Before you start, read about [Personalization](https://documentation.magnolia-cms.com/display/DOCS/Personalization) to understand the terms.

### Create the campaign<a name="create"></a>

1. Go to the app launcher and click the Campaign Manager icon.
![Campaign Manager app]({{ site.baseurl }}/img/start.jpg)

2. Click **Add campaign**.
![Add campaign]({{ site.baseurl }}/img/add_campaign.jpg)<br>

3. Give the campaign the name of "New Year's Eve" and click **Save changes** when you are done.
![Name campaign]({{ site.baseurl }}/img/name_campaign.jpg)

After the campaign is created, you can add it to your pages.

### Add the campaign to a page<a name="add"></a>

1. In the app launcher, click the Pages icon.

2. Click the `demo-project` page and then click **Add to campaign**.
![Activation set]({{ site.baseurl }}/img/activation_set.png)

3. Choose `New-Year-s-Eve` and then click **Save changes** to add the campaign.
![Choose campaign]({{ site.baseurl }}/img/choose_campaign.png)

You can also add the campaign to one or more components belonging to the page (for example, a section). You do this by selecting a component and clicking **Add to campaign** as described above.
![Add to component]({{ site.baseurl }}/img/add_component.jpg)

### Add an image to the campaign<a name="image"></a>

1. Go to the app launcher and click the Assets icon.

2. Under `demo-project`, click the image `staircase-from-above` and then click **Add to campaign**.
![Add image]({{ site.baseurl }}/img/add_image.png)

3. Choose `New-Year-s-Eve` and then click **Save changes** to add the campaign.
![Choose campaign]({{ site.baseurl }}/img/choose_campaign.png)

You can also add a campaign to an entire folder of images by selecting the folder and clicking **Add to campaign**.

### Add a template to the campaign<a name="template"></a>

1. In the app launcher, click the Standard Templating Kit bundle and the Templates icon.
![STK]({{ site.baseurl }}/img/stk.jpg)

2. Under `templating-kit`, click `textImage` and then click **Add to campaign**.
![Text image]({{ site.baseurl }}/img/text-image.jpg)

3. Choose `New-Year-s-Eve` and then click **Save changes** to add the campaign.
![Choose campaign]({{ site.baseurl }}/img/choose_campaign.png)

### Add a resource to the campaign<a name="resource"></a>

1. In the app launcher, click the Resources icon.
![Resources]({{ site.baseurl }}/img/resources.jpg)

2. Under `templating-kit`, click `mobile-scriptloader-plugin` and then click **Add to campaign**.
![Mobile scriptloader]({{ site.baseurl }}/img/mobile-scriptloader.jpg)

3. Choose `New-Year-s-Eve` and then click **Save changes** to add the campaign.
![Choose campaign]({{ site.baseurl }}/img/choose_campaign.png)

### Add a content node to the campaign<a name="node"></a>

1. In the app launcher, click the Configuration icon.
![Configuration]({{ site.baseurl }}/img/config.jpg)

2. Under `modules`, click `contentFeeds` and then click **Add to campaign**.
![Content feed]({{ site.baseurl }}/img/contentFeeds.jpg)

3. Choose `New-Year-s-Eve` and then click **Save changes** to add the campaign.
![Choose campaign]({{ site.baseurl }}/img/choose_campaign.png)

### Reviewing content in the campaign<a name="review"></a>

Once you have added the appropriate amount of content (pages, components, resources, etc.) to the campaign, you can review the content.

1. In the app launcher, click the Campaign Manager icon.

2. Click the `New-Year-s-Eve` campaign and then click any of its content to select it.
![Content review]({{ site.baseurl }}/img/content-review.jpeg)

The colored circles in the `Status` column indicate activation status of the content. See [publication status](https://documentation.magnolia-cms.com/display/DOCS/_Publication+status) for details.

Note the activation colors change depending on the status of the content. For example, if a colleague edits previously published content without republishing it, the activation status changes from green (published) to yellow (modified).

Click **Preview** view unpublished content (indicated by a red or yellow circle). When you are satisfied that the content is correct, click **Review** to indicate it has been reviewed. The colored circle in the `Review` column turns green and the review date is indicated.

### Publishing the content<a name="publish"></a>

Next, select the `New-Year-s-Eve` campaign again and click **Publish**. All content belonging to the campaign becomes versioned and published, and the activation status for all items is green.
![Publish]({{ site.baseurl }}/img/publish.jpg)

### Further reading<a name="reading"></a>

See [Creating and managing campaigns](https://documentation.magnolia-cms.com/login.action?os_destination=%2Fpages%2Fviewpage.action%3FpageId%3D125205787&permissionViolation=true) in the [Campaign Manager](https://documentation.magnolia-cms.com/login.action?os_destination=%2Fpages%2Fviewpage.action%3FpageId%3D125205787&permissionViolation=true) app documentation.


