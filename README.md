# database
database user/calender/event


--------------------------------------------------------------------------
-- MySQL Workbench Forward Engineering

SET @OLD_UNIQUE_CHECKS=@@UNIQUE_CHECKS, UNIQUE_CHECKS=0;
SET @OLD_FOREIGN_KEY_CHECKS=@@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS=0;
SET @OLD_SQL_MODE=@@SQL_MODE, SQL_MODE='TRADITIONAL,ALLOW_INVALID_DATES';

-- -----------------------------------------------------
-- Schema mydb
-- -----------------------------------------------------
-- -----------------------------------------------------
-- Schema sys
-- -----------------------------------------------------

-- -----------------------------------------------------
-- Schema sys
-- -----------------------------------------------------
CREATE SCHEMA IF NOT EXISTS `sys` DEFAULT CHARACTER SET utf8 ;
USE `sys` ;

-- -----------------------------------------------------
-- Table `sys`.`calender`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `sys`.`calender` (
  `calenderID` INT(11) NOT NULL,
  `calenderName` VARCHAR(45) NOT NULL,
  `calenderDateCreated` DATE NOT NULL,
  `calenderDetails` VARCHAR(45) NOT NULL,
  `calenderOwner` VARCHAR(45) NOT NULL,
  `calenderMembers` VARCHAR(45) NULL DEFAULT NULL,
  `calenderTime` INT(11) NULL DEFAULT NULL,
  `calenderDay` INT(11) NULL DEFAULT NULL,
  `calenderMonth` INT(11) NULL DEFAULT NULL,
  `calenderYear` INT(11) NULL DEFAULT NULL,
  `calenderExtra` VARCHAR(45) NULL DEFAULT NULL,
  PRIMARY KEY (`calenderID`))
ENGINE = InnoDB
DEFAULT CHARACTER SET = utf8;


-- -----------------------------------------------------
-- Table `sys`.`event`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `sys`.`event` (
  `EventID` INT(11) NOT NULL,
  `EventName` VARCHAR(45) NOT NULL,
  `EventDateCreated` DATE NOT NULL,
  `EventDetails` VARCHAR(45) NOT NULL,
  `EventLocation` VARCHAR(45) NULL DEFAULT NULL,
  `EventStart` DATE NULL DEFAULT NULL,
  `EventEnd` DATE NULL DEFAULT NULL,
  `EventTime` VARCHAR(45) NULL DEFAULT NULL,
  `EventMembers` VARCHAR(45) NOT NULL,
  `EventIsUnderThisCalender` VARCHAR(45) NOT NULL,
  `EventExtra` VARCHAR(45) NULL DEFAULT NULL,
  PRIMARY KEY (`EventID`))
ENGINE = InnoDB
DEFAULT CHARACTER SET = utf8;


-- -----------------------------------------------------
-- Table `sys`.`sys_config`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `sys`.`sys_config` (
  `variable` VARCHAR(128) NOT NULL,
  `value` VARCHAR(128) NULL DEFAULT NULL,
  `set_time` TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  `set_by` VARCHAR(128) NULL DEFAULT NULL,
  PRIMARY KEY (`variable`))
ENGINE = InnoDB
DEFAULT CHARACTER SET = utf8;


-- -----------------------------------------------------
-- Table `sys`.`user`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `sys`.`user` (
  `UserID` INT(11) NOT NULL,
  `UserType` INT(11) NOT NULL,
  `UsernName` VARCHAR(45) NOT NULL,
  `UserAge` VARCHAR(45) NOT NULL,
  `UserEmail` VARCHAR(45) NOT NULL,
  `UserPhone` INT(11) NULL DEFAULT NULL,
  `UserNationality` VARCHAR(45) NULL DEFAULT NULL,
  `UserAdress` VARCHAR(45) NULL DEFAULT NULL,
  `UserRole` VARCHAR(45) NOT NULL,
  `UserRecord` VARCHAR(45) NULL DEFAULT NULL,
  `UserPassword` VARCHAR(45) NOT NULL,
  `UserFriendList` VARCHAR(45) NULL DEFAULT NULL,
  `UserCalenders` VARCHAR(45) NULL DEFAULT NULL,
  `UserSubscribedToThisCalender` VARCHAR(45) NULL DEFAULT NULL,
  `UserEvents` VARCHAR(45) NULL DEFAULT NULL,
  `UserExtra` VARCHAR(45) NULL DEFAULT NULL,
  PRIMARY KEY (`UserID`))
ENGINE = InnoDB
DEFAULT CHARACTER SET = utf8;


-- -----------------------------------------------------
-- Table `sys`.`userconfig`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `sys`.`userconfig` (
  `UserConfiqID` INT(11) NOT NULL,
  `UserConfigPassword` VARCHAR(45) NULL DEFAULT NULL,
  `UserConfigExtra` VARCHAR(45) NULL DEFAULT NULL,
  PRIMARY KEY (`UserConfiqID`))
ENGINE = InnoDB
DEFAULT CHARACTER SET = utf8;


SET SQL_MODE=@OLD_SQL_MODE;
SET FOREIGN_KEY_CHECKS=@OLD_FOREIGN_KEY_CHECKS;
SET UNIQUE_CHECKS=@OLD_UNIQUE_CHECKS;
