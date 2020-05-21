# Uncomment the next line to define a global platform for your project
# platform :ios, '9.0'

target 'MBaseDemo' do
  # Comment the next line if you don't want to use dynamic frameworks
  use_frameworks!

  # Pods for MBaseDemo
  pod 'MBaseSDK'

  post_install do |installer|
    puts "##### Prepare MBaseSDK start #####"
    project_name = Dir.glob("*.xcodeproj").first.gsub(".xcodeproj", "")
    main_pod_name = "Pods-" + project_name

    mbase_header = Dir.pwd + '/Pods/MBaseSDK/MBaseSDK/Public/MBaseHeader.swift'

    group = installer.pods_project.pod_group('MBaseSDK')
    reference = installer.pods_project.add_file_reference(mbase_header, group)
    installer.pods_project.targets.each do |target|
      if target.name == main_pod_name
        puts " Add mbase_header to #{main_pod_name}"
        target.add_file_references([ reference ])
      end
    end
    puts "##### Prepare MBaseSDK end #####"    
  end
end
