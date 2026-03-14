AI Media Processing Pipeline (AWS Serverless)

A serverless AI-powered media processing pipeline built on AWS that automatically analyzes uploaded videos, transcribes speech, generates summaries using AI, and stores metadata for downstream applications.

This project demonstrates event-driven architecture, serverless compute, and generative AI integration using AWS services.
Workflow

User uploads a video file to S3

EventBridge detects the upload event

Step Functions pipeline starts

Video is analyzed using Amazon Rekognition

Audio is transcribed using Amazon Transcribe

Transcript is processed and summarized using Amazon Bedrock

Metadata and summary are stored in DynamoDB
Lambda Functions
video-analyzer

Uses Amazon Rekognition to detect objects and labels in the uploaded video.

video-transcriber

Starts a Transcribe job to convert video audio into text.

video-summarizer

Uses Amazon Bedrock (Claude) to generate a concise summary of the transcript.

Includes safety filtering to block inappropriate content.

video-metadata

Stores results in DynamoDB including:

video file name

Rekognition labels

transcription

AI summary

safety status
Deployment

Create an S3 bucket for uploads

Deploy Lambda functions

Configure Step Functions workflow

Create EventBridge trigger for S3 uploads

Enable Bedrock model access

Sample Use Cases

AI-powered media intelligence platform

Automated video moderation

Podcast summarization

Content indexing for search

AI-driven media analytics
