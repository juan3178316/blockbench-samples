---
title: "Blockbench samples"
description: "Get samples about how works the blockbench types documentation"
author: juan3178316
date: 2025-10-23
---

# Index.d.ts documentation

## Classes
+ [Deletable](classes/deletable.md)
+ [Plugin](classes/plugin.md)
+ [Panel](classes/panel.md)
+ [Property](classes/property.md)

## Enumerations

## Interfaces
+ [MessageBoxOptions](interfaces/message-box-options.md)
+ [PluginData](interfaces/plugin-data.md)
+ [PanelOptions](interfaces/panel-options.md)
+ [PropertyOptions](interfaces/property-options.md)

## type Aliases
+ [EventName](type-aliases/event-name.md)
+ [IconString](type-aliases/icon-string.md)
+ [Condition](type-aliases/condition.md)

## Errors

---

## Constants

### isApp

`isApp: boolean`

True if Blockbench runs as a native app

type: _boolean_

## Namespaces
```javascript
declare namespace Blockbench {
	const platform: 'web' | 'win32' | 'darwin' | 'linux'
	const version: string
	/**
	 * Time when Blockbench was opened
	 */
	const openTime: Date
	function reload(): void
	/**
	 * checks if Blockbench is newer than the specified version
	 * 
	 * @param version
	 * semver string
	 */
	function isNewerThan(version: string): boolean
	/**
	 * checks if Blockbench is older than the specified version
	 * 
	 * @param version
	 * semver string
	 */
	function isOlderThan(version: string): boolean
	/**
	 * Resolves an icon string as a HTML element
	 * @param icon 
	 * Material Icons, Fontawesome or custom icon string
	 * @param color 
	 * CSS color
	 */
	function getIconNode(icon: IconString, color?: string): HTMLElement
	/**
	 * Shows a passing message in the middle of the screen
	 * 
	 * @param message 
	 * Message
	 * @param time 
	 * Time in miliseconds that the message stays up
	 */
	function showQuickMessage(message: string, time?: number): void

	function showStatusMessage(message: string, time?: number): void

	function setStatusBarText(text?: string): void
	/**
	 * Set the value of a progress bar
	 * 
	 * @param progress 
	 * Progress of the bar between 0 and 1
	 * @param time 
	 * Time over which the bar is animated, in miliseconds
	 * @param bar
	 * ID of the bar element. If omitted, the main status bar will be selected
	 */
	function setProgress(progress: number, time?: number, bar?: string): void

	/**
	 * Opens a message box
	 */
	function showMessageBox(options: MessageBoxOptions, callback: (buttonID: number) => void): void

	function textPrompt(title: string, value: string, callback: (value: string) => void): void
	/**
	 * Opens the specified link in the browser or in a new tab
	 */
	function openLink(link: URL): void

	/**
	 * Shows a system notification
	 * @param title Title
	 * @param text Text
	 * @param icon Url or data url pointing to an icon. Defaults to Blockbench icon
	 */
	function notification(title: string, text: string, icon?: string): void
	/**
	 * Adds custom CSS code to Blockbench, globally. Returns an object that is deletable
	 * @param css CSS string
	 */
	function addCSS(css: string): Deletable

	function addFlag(flag: string): void
	function removeFlag(flag: string): void
	function hasFlag(flag: string): boolean

	function dispatchEvent(event_name: EventName, data: object): void

	function addListener(event_names: EventName, callback: (data: object) => void): void
	function on(event_names: EventName, callback: (data: object) => void): void

	function removeEventListener(event_names: EventName): void
}
```