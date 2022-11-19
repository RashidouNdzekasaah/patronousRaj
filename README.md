Resources:
  MySG:
    Type: AWS::EC2::SecurityGroup
    DeletionPolicy: Retain
    Properties:
      GroupDescription: Enable SSH access via port 22
      SecurityGroupIngress:
      - CidrIp: 0.0.0.0/0
        FromPort: 22
        IpProtocol: tcp
        ToPort: 22

  MyEBS:
    Type: AWS::EC2::Volume
    DeletionPolicy: Snapshot
    Properties:
      AvailabilityZone: us-east-1a
      Size: 1
      VolumeType: gp2
