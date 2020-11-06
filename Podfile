# Uncomment the next line to define a global platform for your project
# platform :ios, '9.0'

target 'MBaseDemo' do
  # Comment the next line if you don't want to use dynamic frameworks
  use_frameworks!

  # Pods for MBaseDemo
  pod 'MBaseSDK'
end


post_install do |installer|
  installer.pods_project.build_configurations.each do |config|
    next unless config.name == 'Debug'
    config.build_settings['LD_RUNPATH_SEARCH_PATHS'] = [
      '$(FRAMEWORK_SEARCH_PATHS)'
    ]
  end
end