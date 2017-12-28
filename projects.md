---
layout: default
title: Sergii Bomko - Code that Might be Useful to You
---

<style>
.list {
    margin: 8px 0 24px 0;
}
.list .header-container {
    height: 30px;
    line-height: 30px;
    position: relative;
    font-size: 20px;
    text-decoration: none;
}
.item-list-container {
    display: inline-block;
    position: relative;
    width: 100%;
    color: #000;
}
.item-list-container .item {
    float: left;
    margin-right: 13.5px;
    margin-top: 16px;
}
.item-card {
    background-color: #fff;
    font-size: 12px;
    width: 182px;
    height: 246px;
    border-radius: 0;
    border: 1px solid #fff;
    cursor: pointer;
    -moz-box-shadow: 2px 2px 5px rgba(0,0,0,.1);
    -webkit-box-shadow: 2px 2px 5px rgba(0,0,0,.1);
    box-shadow: 2px 2px 5px rgba(0,0,0,.1);
    position: relative;
    overflow: hidden;
}
.item-card .icon-cell {
    text-align: center;
    padding: 16px 0;
}
.item-card .icon-cell>img {
    max-width: 85%;
    height: 72px;
}
.home-page-view img {
    border-style: none;
}
.item-card .core-info-cell {
    padding: 0 10px;
    position: relative;
}
.item-card .core-info-cell .name {
    font-size: 14px;
    font-family: Segoe UI,wf_segoe-ui_normal,-apple-system,".SFNSText-Regular","San Francisco","Roboto","Helvetica Neue","Lucida Grande",sans-serif;
    font-weight: 600;
    white-space: nowrap;
    overflow: hidden;
    position: relative;
    color: inherit;
}
.item-card .details {
    margin-top: 10px;
    padding: 0 10px;
}
.item-card .description {
    height: 4.4em;
    overflow: hidden;
    color: #767676;
    display: -webkit-box;
    -webkit-line-clamp: 3;
    -webkit-box-orient: vertical;
    overflow: hidden;
    text-overflow: ellipsis;
}
.item-card .text-fadeout {
    height: 100%;
    width: 30px;
    background: linear-gradient(to right,rgba(255,255,255,0),#fff);
    position: absolute;
    right: 0;
    top: 0;
    display: block;
}
.item-card .links {
    position: relative;
    height: 20px;
    margin-top: 16px;
    padding: 0 10px;
}
</style>

<h1>Open Source Projects</h1>
<hr/>

<div class="list">
	<div class="header-container">
		<div class="header">
			<span class="category">Services</span>
		</div>
	</div>
	<div class="item-list-container">
		<div class="item">
			<a href="https://github.com/nHook">
				<div class="item-card" title="nHook">
					<div class="cover">
						<div class="icon-cell">
							<img class="item-icon" src="http://nhook.github.io/content/logo.png" title="nHook" />
						</div>
						<div class="core-info-cell">
							<div class="name">
								<span>nHook - OUTDATED</span>
								<span class="text-fadeout"></span>
							</div>
						</div>
					</div>
					<div class="details">
						<div class="description" title="nHook is a service that can build and publish your package into NuGet. The nHook service can be applied to your GitHub or BitBucket repository and automatically build your project after pushing your changes.">nHook is a service that can build and publish your package into NuGet. The nHook service can be applied to your GitHub or BitBucket repository and automatically build your project after pushing your changes.</div>
					</div>
					<div class="links">
						<a href="http://nhook.github.io/">nHook docs</a>
					</div>
				</div>
			</a>
		</div>
	</div>
</div>
<div class="list">
	<div class="header-container">
		<div class="header">
			<span class="category">Tools and libraries</span>
		</div>
	</div>
	<div class="item-list-container">
		<div class="item">
			<a href="https://github.com/aquiladev/AquilaDev.Owin.Security.LaunchKey">
				<div class="item-card" title="AquilaDev.Owin.Security.LaunchKey">
					<div class="cover">
						<div class="icon-cell">
							<img class="item-icon" src="https://raw.githubusercontent.com/aquiladev/aquiladev.github.io/master/images/launchkey_icon.png" title="AquilaDev.Owin.Security.LaunchKey" />
						</div>
						<div class="core-info-cell">
							<div class="name">
								<span>AquilaDev.Owin.Security.LaunchKey</span>
								<span class="text-fadeout"></span>
							</div>
						</div>
					</div>
					<div class="details">
						<div class="description" title="Middleware that enables an application to use LaunchKey's OAuth 2.0 authentication workflows.">Middleware that enables an application to use LaunchKey's OAuth 2.0 authentication workflows.</div>
					</div>
					<div class="links">
						<a href="https://www.nuget.org/packages/AquilaDev.Owin.Security.LaunchKey">Pack</a>,
						<a href="https://launchkey.com">LaunchKey</a>
					</div>
				</div>
			</a>
		</div>
		<div class="item">
			<a href="https://github.com/aquiladev/chromypack">
				<div class="item-card" title="chromypack">
					<div class="cover">
						<div class="icon-cell">
							<img class="item-icon" src="https://raw.githubusercontent.com/aquiladev/aquiladev.github.io/master/images/chromium_icon.png" title="chromypack" />
						</div>
						<div class="core-info-cell">
							<div class="name">
								<span>chromypack</span>
								<span class="text-fadeout"></span>
							</div>
						</div>
					</div>
					<div class="details">
						<div class="description" title="Generating package for ChromeDriver. The library can check ChromeDriver updates and generate NuGet package with it.">Generating package for ChromeDriver. The library can check ChromeDriver updates and generate NuGet package with it.</div>
					</div>
					<div class="links">
						<a href="https://www.nuget.org/packages/Chromium.ChromeDriver">ChromeDriver pack</a>
					</div>
				</div>
			</a>
		</div>
		<div class="item">
			<a href="https://github.com/aquiladev/SkyDrive.FileWatcher">
				<div class="item-card" title="SkyDrive.FileWatcher">
					<div class="cover">
						<div class="icon-cell">
							<img class="item-icon" src="https://raw.githubusercontent.com/aquiladev/aquiladev.github.io/master/images/one_drive.png" title="SkyDrive.FileWatcher" />
						</div>
						<div class="core-info-cell">
							<div class="name">
								<span>SkyDrive.FileWatcher</span>
								<span class="text-fadeout"></span>
							</div>
						</div>
					</div>
					<div class="details">
						<div class="description" title="Package is made for tracking files transformations in OneDrive.">Package is made for tracking files transformations in OneDrive.</div>
					</div>
					<div class="links">
						<a href="https://www.nuget.org/packages/SkyDrive.FileWatcher">Pack</a>
					</div>
				</div>
			</a>
		</div>
	</div>
</div>
<div class="list">
	<div class="header-container">
		<div class="header">
			<span class="category">Build and release</span>
		</div>
	</div>
	<div class="item-list-container">
		<div class="item">
			<a href="https://github.com/aquiladev/vsts-kudu-tasks">
				<div class="item-card" title="VSTS Kudu Tasks">
					<div class="cover">
						<div class="icon-cell">
							<img class="item-icon" src="https://raw.githubusercontent.com/aquiladev/vsts-kudu-tasks/master/Extension/icon.png" title="VSTS Kudu Tasks" />
						</div>
						<div class="core-info-cell">
							<div class="name">
								<span>VSTS Kudu Tasks</span>
								<span class="text-fadeout"></span>
							</div>
						</div>
					</div>
					<div class="details">
						<div class="description" title="Extension that enable you to integrate with Kudu.">Extension that enable you to integrate with Kudu.</div>
					</div>
					<div class="links">
						<a href="https://marketplace.visualstudio.com/items?itemName=sergiibomko.vsts-kudu-tasks">Extension</a>
					</div>
				</div>
			</a>
		</div>
		<div class="item">
			<a href="https://github.com/aquiladev/vsts-trigger">
				<div class="item-card" title="VSTS Trigger">
					<div class="cover">
						<div class="icon-cell">
							<img class="item-icon" src="https://raw.githubusercontent.com/aquiladev/vsts-trigger/master/Extension/icon.png" title="VSTS Trigger" />
						</div>
						<div class="core-info-cell">
							<div class="name">
								<span>VSTS Trigger</span>
								<span class="text-fadeout"></span>
							</div>
						</div>
					</div>
					<div class="details">
						<div class="description" title="Extension that enable you to trigger release process.">Extension that enable you to trigger release process.</div>
					</div>
					<div class="links">
						<a href="https://marketplace.visualstudio.com/items?itemName=sergiibomko.vsts-trigger">Extension</a>
					</div>
				</div>
			</a>
		</div>
	</div>
</div>
<div class="list">
	<div class="header-container">
		<div class="header">
			<span class="category">Visual Studio extensions</span>
		</div>
	</div>
	<div class="item-list-container">
		<div class="item">
			<a href="https://github.com/aquiladev/Coding4Fun.WorkspaceBox">
				<div class="item-card" title="Coding4Fun.WorkspaceBox">
					<div class="cover">
						<div class="icon-cell">
							<img class="item-icon" src="https://raw.githubusercontent.com/aquiladev/Coding4Fun.WorkspaceBox/master/Coding4Fun.WorkspaceBox/Resources/WorkspaceBox.png" title="Coding4Fun.WorkspaceBox" />
						</div>
						<div class="core-info-cell">
							<div class="name">
								<span>Coding4Fun.WorkspaceBox</span>
								<span class="text-fadeout"></span>
							</div>
						</div>
					</div>
					<div class="details">
						<div class="description" title="This extension displays the current workspace by its location and therefore will significantly help you to speed up.">This extension displays the current workspace by its location and therefore will significantly help you to speed up.</div>
					</div>
					<div class="links">
						<a href="https://visualstudiogallery.msdn.microsoft.com/ebf0d6c0-2e9b-4e99-80e3-4a716307bcb7">VS 2013</a>,
						<a href="https://visualstudiogallery.msdn.microsoft.com/12b30529-9a53-4c84-a1c2-381438eb1186">VS 2012</a>
					</div>
				</div>
			</a>
		</div>
		<div class="item">
			<a href="https://github.com/aquiladev/Coding4Fun.TfsAnalytics">
				<div class="item-card" title="Coding4Fun.TfsAnalytics">
					<div class="cover">
						<div class="icon-cell">
							<img class="item-icon" src="https://raw.githubusercontent.com/aquiladev/Coding4Fun.TfsAnalytics/master/src/Coding4Fun.TfsAnalyticsPackage/Resources/Package.png" title="Coding4Fun.TfsAnalytics" />
						</div>
						<div class="core-info-cell">
							<div class="name">
								<span>Coding4Fun.TfsAnalytics</span>
								<span class="text-fadeout"></span>
							</div>
						</div>
					</div>
					<div class="details">
						<div class="description" title="This extension is designed to measure the time spent for the task's completion.">This extension is designed to measure the time spent for the task's completion.</div>
					</div>
					<div class="links">
						<a href="https://visualstudiogallery.msdn.microsoft.com/0a08eaa8-87e9-4e75-a04f-b9dffa73f025">VS 2013</a>,
						<a href="https://visualstudiogallery.msdn.microsoft.com/3bbae6fd-45df-40e0-ac15-9738e90ce0bc">VS 2012</a>
					</div>
				</div>
			</a>
		</div>
	</div>
</div>
<div class="list">
	<div class="header-container">
		<div class="header">
			<span class="category">Devices and hardware</span>
		</div>
	</div>
	<div class="item-list-container">
		<div class="item">
			<a href="https://github.com/aquiladev/bicycle_wheel_beacon">
				<div class="item-card" title="Bicycle beacon">
					<div class="cover">
						<div class="icon-cell">
							<img class="item-icon" src="https://raw.githubusercontent.com/aquiladev/aquiladev.github.io/master/images/beacon.png" title="Bicycle beacon" />
						</div>
						<div class="core-info-cell">
							<div class="name">
								<span>Bicycle beacon</span>
								<span class="text-fadeout"></span>
							</div>
						</div>
					</div>
					<div class="details">
						<div class="description" title="The proof of concept for device with same functionality like revolights project from kickstarter.">The proof of concept for device with same functionality like revolights project from kickstarter.</div>
					</div>
					<div class="links">
						<a href="https://vimeo.com/52921155">Video</a>,
						<a href="http://revolights.com">Revolights</a>
					</div>
				</div>
			</a>
		</div>
	</div>
</div>
