# CricScorer - Live Cricket Scoring WordPress Plugin

A smart WordPress plugin that displays live cricket scores, match details, and commentary just using PHP and wordpress ecosystem and compatible with all types of wordpress plugin. Perfect for cricket websites, sports blogs, and news portals. Best Cricket Live scoring script or wordpress plugin. 

## 🏏 Features

### Core Functionality
- **Live Match Scores**: Real-time cricket scores with automatic updates
- **Match Commentary**: Live ball-by-ball commentary and match updates
- **Match Details**: Comprehensive match information including team lineups, toss results, and match status
- **Multiple Formats**: Support for Test matches, ODIs, T20Is, and other cricket formats
- **Auto-Refresh**: Configurable automatic data refresh for live updates
- **Smart Caching**: Intelligent caching system to optimize performance and reduce API calls

### Display Features
- **Responsive Design**: Mobile-friendly layouts that work on all devices
- **Modern UI**: Clean, professional design that integrates seamlessly with your theme
- **Team Logos**: Automatic team logo display for better visual appeal
- **Match Cards**: Beautiful match cards with scores, status, and series information
- **Live Commentary Feed**: Real-time commentary updates with smooth scrolling
- **Scoreboard**: Detailed scoreboard with batsman stats, bowling figures, and run rates

### Technical Features
- **AJAX-Powered**: Smooth user experience with AJAX-based data loading
- **Error Handling**: Robust error handling with fallback options
- **Debug Mode**: Built-in debugging tools for troubleshooting
- **Performance Optimized**: Smart caching and minimal resource usage
- **Theme Compatible**: Works with any WordPress theme
- **SEO Friendly**: Clean HTML output optimized for search engines

## 📦 Installation

### Method 1: Manual Installation
1. Download the plugin files
2. Upload the `cricscorer` folder to `/wp-content/plugins/` directory
3. Activate the plugin through the 'Plugins' menu in WordPress
4. Go to **Settings → CricScorer** to configure the plugin

### Method 2: WordPress Admin Upload
1. Go to **Plugins → Add New** in your WordPress admin
2. Click **Upload Plugin**
3. Choose the plugin zip file and click **Install Now**
4. Activate the plugin after installation

## ⚙️ Configuration

Navigate to **Settings → CricScorer** in your WordPress admin to configure:

### General Settings
- **Auto Refresh Interval**: Set how often data refreshes (5-300 seconds)
- **Cache Duration**: Configure how long data is cached (60-3600 seconds)
- **Smart Refresh Mode**: Enable intelligent refresh to reduce unnecessary API calls
- **Debug Mode**: Enable detailed logging for troubleshooting

### Recommended Settings
- **Refresh Interval**: 20 seconds for live matches
- **Cache Duration**: 300 seconds (5 minutes) for optimal performance
- **Smart Refresh**: Enabled for better performance

## 🎯 Usage

### Shortcodes

#### Display Live Matches
```php
[cricscorer_matches]
```

**Parameters:**
- `limit="10"` - Number of matches to display (default: 10)
- `auto_refresh="true"` - Enable/disable auto-refresh (default: true)
- `show_format="true"` - Show/hide match format badges (default: true)
- `debug="false"` - Enable debug information (default: false)

**Examples:**
```php
[cricscorer_matches limit="15"]
[cricscorer_matches auto_refresh="false"]
[cricscorer_matches show_format="false"]
```

#### Display Match Details
```php
[cricscorer_match]
```

**Parameters:**
- `match_id="117359"` - Specific match ID (optional if using URL parameter)
- `auto_refresh="true"` - Enable/disable auto-refresh (default: true)

**Examples:**
```php
[cricscorer_match match_id="117359"]
[cricscorer_match auto_refresh="false"]
```

### URL-Based Match Display

The plugin supports URL-based match display for better SEO and user experience:

```
yoursite.com/match/?id=117359
```

This automatically loads the match detail shortcode with the specified match ID.

### Testing Shortcodes

Use these shortcodes to test plugin functionality:

```php
[cricscorer_test]           // Basic functionality test
[cricscorer_sample]          // Sample match display
[cricscorer_diagnostic]      // System diagnostic information
```

## 🎨 Styling & Customization

### CSS Classes

The plugin uses semantic CSS classes for easy customization:

```css
.cricscorer-matches-container    /* Main container */
.cricscorer-match-card          /* Individual match card */
.cricscorer-match-title         /* Match title */
.cricscorer-team-score          /* Team score display */
.cricscorer-match-status        /* Match status */
.cricscorer-live-score          /* Live score section */
.cricscorer-commentary          /* Commentary section */
```

### Custom Styling

Add custom CSS to your theme's `style.css` or use WordPress Customizer:

```css
/* Customize match cards */
.cricscorer-match-card {
    border-radius: 8px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.1);
}

/* Customize team colors */
.cricscorer-team-name {
    font-weight: bold;
    color: #333;
}
```

## 🔧 Advanced Configuration

### Custom Template

Create a custom template by copying `templates/match-detail.php` to your theme:

```
your-theme/cricscorer/match-detail.php
```

### Hooks & Filters

The plugin provides several hooks for developers:

```php
// Modify match data before display
add_filter('cricscorer_match_data', 'your_custom_function');

// Add custom content to match cards
add_action('cricscorer_match_card_footer', 'your_custom_content');
```

### AJAX Endpoints

Available AJAX endpoints for custom development:

- `cricscorer_get_matches` - Fetch match list
- `cricscorer_get_match_details` - Fetch match details
- `cricscorer_render_match_detail` - Render match detail HTML

## 🚀 Performance Optimization

### Caching Strategy
- **Smart Caching**: Only refreshes when data actually changes
- **Transient Storage**: Uses WordPress transients for efficient caching
- **Minimal API Calls**: Reduces server load with intelligent refresh

### Best Practices
1. **Set Appropriate Limits**: Use reasonable match limits to avoid performance issues
2. **Enable Caching**: Keep caching enabled for better performance
3. **Monitor Refresh Intervals**: Balance between live updates and server load
4. **Use Debug Mode Sparingly**: Only enable when troubleshooting

## 🐛 Troubleshooting

### Common Issues

#### Matches Not Loading
1. Check if the plugin is activated
2. Verify internet connectivity
3. Enable debug mode and check error logs
4. Test with `[cricscorer_test]` shortcode

#### Styling Issues
1. Check theme compatibility
2. Verify CSS files are loading
3. Test with `[cricscorer_sample]` shortcode
4. Check for CSS conflicts

#### Performance Issues
1. Increase cache duration
2. Reduce refresh frequency
3. Limit number of matches displayed
4. Enable smart refresh mode

### Debug Information

Enable debug mode in settings to get detailed logs:
- WordPress error log: `/wp-content/debug.log`
- Plugin debug information via shortcodes
- Browser developer tools for AJAX errors

### Support

For technical support:
1. Check WordPress error logs
2. Enable debug mode
3. Test with sample shortcodes
4. Verify plugin activation and permissions

## 📱 Mobile Optimization

- **Responsive Design**: Automatically adapts to mobile screens
- **Touch-Friendly**: Optimized for touch interactions
- **Reduced Data Usage**: Smart loading and caching
- **Fast Loading**: Optimized for mobile networks

## 🔒 Security Features

- **Nonce Verification**: All AJAX requests are secured
- **Data Sanitization**: All output is properly escaped
- **Permission Checks**: Admin functions require proper permissions
- **Input Validation**: All user inputs are validated

## 📊 System Requirements

- **WordPress**: 5.0 or higher
- **PHP**: 7.4 or higher
- **MySQL**: 5.6 or higher
- **Memory**: Minimum 128MB PHP memory limit
- **Internet**: Stable internet connection for live data

## 🆕 Version History

### Version 1.0.0
- Initial release
- Live match scores and commentary
- Responsive design
- Smart caching system
- Admin settings panel
- Multiple shortcode options

## 📄 License

This plugin is licensed under the GPL v2 or later.

## 🤝 Contributing

Contributions are welcome! Please ensure:
- Code follows WordPress coding standards
- All functions are properly documented
- Security best practices are followed
- Performance impact is considered

## 📞 Support & Documentation

For additional support and documentation:
- Check the plugin settings page for configuration help
- Use debug shortcodes for troubleshooting
- Review WordPress error logs for detailed error information
- Test with sample shortcodes to verify functionality

---

**CricScorer** - Bringing live cricket action to your WordPress site! 🏏
