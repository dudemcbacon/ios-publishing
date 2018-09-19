pipeline {
    agent { label 'mac' }

    parameters {
      string(name: 'VERSION_NUMBER', description: 'The version number to set on the iOS App')
      string(name: 'BUILD_NUMBER', defaultValue: '0', description: 'The build number to set on the iOS App')
    }

    stages {
        stage('Download code from SFTP') {
          steps {
            // Download LMContent_prd_2.zip
            // Download MAP_RF_2.X.zip
          }
        }
        stage('Unzip code') {
          steps {
            // Unzip MAP_RF_2.X.zip to /root/
            // Unzip LMContent_prd_2.zip to /root/iOS/Data/Raw/LMContent
          }
        }
        stage('Change permissions') {
          steps {
            sh 'chmod a+x MapFileParser.sh'
            sh 'chmod a+x process_symbols.sh'
            sh 'chmod a+x MapFileParser'
          }
        }
        stage('Update confix.xml') {
          steps {
            // Move prd config (Data\Raw\Config\prod) to root config.xml directory
            // Update <vpAppleStoreVersion> to $VERSION_NUMBER
          }
        }
        stage('Configure XCode (App Name, Display Name, and Bundle ID)') {
          steps {
            // Change Name to 'MAP Reading Fluency Testing'
            // Change Display Name to 'MAP RF'
            // Change Bundle ID to 'org.nwea.map-reading-fluency'
            // Change Version Number to $VERSION_NUMBER
            // Set Build Number to $BUILD_NUMBER
          }
        }
        stage('Build') {
            steps {
                // Xcode command to build application
                echo 'Building..'
            }
        }
        stage('Archive') {
            steps {
                // Xcode command to archive app
            }
        }
        stage('Publish') {
            steps {
              // Create version in iTunes Connect (with a command line tool)
                // What's new
              // Publish (with a command line tool, preferably)
            }
        }
        stage('Send e-mail that iOS was published')
        stage('Wait for approval') {
        }
        stage('Send e-mail that iOS app was approved')
        stage('Release')
    }
}
