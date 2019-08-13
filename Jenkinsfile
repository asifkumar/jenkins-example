node {
    try {
        sh 'exit 1'
        currentBuild.result = 'SUCCESS'
    } catch (any) {
        currentBuild.result = 'FAILURE'
        throw any //rethrow exception to prevent the build from proceeding
    } finally {
        step([$class: 'Mailer', notifyEveryUnstableBuild: true, recipients: 'asifdevops.com', sendToIndividuals: true])
    }
}
