pipeline {
    agent any

    environmten {
        MSBUILD = 'C:\\Program Files (x86)\\MSBuild\\14.0\\Bin\\MSBuild.exe'
        CONFIG = 'Release'
        PLATFORM = 'AnyCPU'
        SLN_NAME = 'JenkinsWebProjectSkillup.sln'
    }

    stages {
        stage('Build') {
            steps {
                bat "Nuget.exe restore ${SLN_NAME}"
                bat "\"${MSBUILD}\" ${SLN_NAME} /p:Configuration${env.CONFIG};Platform=${env.PLATFORM} /maxcpucount:%NUMBER_OF_PROCESSORS% /nodeReuse:false"
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}